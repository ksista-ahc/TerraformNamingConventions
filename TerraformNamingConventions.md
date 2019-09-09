# Terraform Naming Guidelines

This file provides a quick view of the guidance for Azure Services using Terraform.

### Definitions

* __snake_case__: using an underscore `_` to separate 'words' in a variable name.
* __kebab-case__: using a hyphen `-` to separate 'words' in a variable name.
* __camelCase__: using a Capital letter to separate 'words' starting with a lowercase letter.
* __PascalCase__: using a Capital letter to separate 'words' starting with an uppercase letter.

## Variables and Locals

> Use descriptive identifiers, with `snake_case` for variables and locals.
>
> * __case:__       snake_case
> * __characters:__   a-z _
>
> ``` cs
> variable "azurerm_subscription_id" {
>   description = "The Azure subscription ID to use."
>   default = "optional Default value. (see note below)"
> }
> ```
>
> > #### Default values
> > Provide default values for variables that are not critical to the targetted deployment.
> >  



## Resources
>
> Use descriptive values for Resource names.
> These can be referenced inside the script in order to share details of created resources.
>
> * __case:__       snake_case
> * __characters:__   a-z _
>
> #### Examples
> ``` cs
> resource "azurerm_resource_group" "rg" {...}
>
> resource "azurerm_public_ip" "public_ip" {...}
> ```
>
> These two examples can be referenced anywhere else in the script as:
> - `${azurerm_resource_group.rg.location}` \*
> - `${azurerm_public_ip.public_ip.ip_address}` \*
>
> \* see [Terraform Documentation](https://www.terraform.io/docs/providers/azurerm/index.html) for details on what fields are available for:
> * [Azure Resource Groups](https://www.terraform.io/docs/providers/azurerm/r/resource_group.html)
> * [Public IP](https://www.terraform.io/docs/providers/azurerm/r/public_ip.html)


### Resource Names
> When creating Azure Resources in Terraform scripts be sure to follow the guidance in [Azure Naming Conventions](./AzureNamingConvensions.md) when defining the `name` property.
>
>
>
> ``` cs
> resource "azurerm_resource_group" "rg" {
>  name     = "${var.prefix}-${var.environment}-rg"
>  location = "${var.location}"
>
>  tags {
>    environment = "${var.environment}"
>  }
>}
> ```



## Outputs
>
> Use descriptive identifiers, with `snake_case` for output parameters.
>
> * __case:__       snake_case
> * __characters:__   a-z _
>
> ``` cs
> output "data_public_ip" {
>   value = "${data.azurerm_public_ip.public_ip.ip_address}"
> }
> ```
> or, when referencing output of an external tool the returns JSON formatted data:
> ``` cs
> output "cert_info" {
>   value = "${data.external.get_thumbprint_and_uri.result["thumbprint"]}"
> }
> ```
