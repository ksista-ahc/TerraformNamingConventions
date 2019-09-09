# Azure Resources Naming Guidelines

There are rules and guidelines for names given to Azure Resources - see [Azure Naming Conventions](https://docs.microsoft.com/en-us/azure/architecture/best-practices/naming-conventions) for additional details

This file provides a quick overview of this guidance for any service running in Azure.

### Definitions

* __snake_case__: using an underscore `_` to separate 'words' in a variable name.
* __kebab-case__: using a hyphen `-` to separate 'words' in a variable name.
* __camelCase__: using a Capital letter to separate 'words' starting with a lowercase letter.
* __PascalCase__: using a Capital letter to separate 'words' starting with an uppercase letter.


### Environments
>
> * dev   - Development
> * acc   - Acceptance Testing
> * prod  - Production
>


## Summary Table

| Resource                     | Format                                                         | case               | Characters         | Length | Example                           |
| ---------------------------- | -------------------------------------------------------------- | ------------------ | ------------------ | ------ | --------------------------------- |
| Resource Group               | <service short name>-<environment>-rg                          | kebab-case         | a-z 0-9 - _ . ( )  | 1-90   | companycloud-acc-rg                 |
| App Service Plan             | <service short name>-<environment>-sp                          | kebab-case         | a-z 0-9 -          | 1-40   | companycloud-acc-sp                 |
| Application Insights         | <service short name>-<environment>-ai                          | kebab-case         | a-z 0-9 - _ . ( )  | 1-255  | companycloud-acc-ai                 |
| Availability Set             | <service short name>-<environment>-as                          | kebab-case         | a-z 0-9 -          | 1-80   | companycloud-acc-as                 |
| Key Vault                    | <service short name>-<environment>-kv                          | kebab-case         | a-z 0-9 -          | 3-24   | companycloud-acc-kv                 |
| Load Balancer                | <service short name>-<environment>-lb                          | kebab-case         | A-Z a-z 0-9 - _ .  | 1-80   | companycloud-acc-lb                 |
| Public IP                    | <service short name>-<environment>-publicip                    | kebab-case         | a-z 0-9 - _ .      | 1-80   | companycloud-acc-publicip           |
| Service Bus                  | <service short name>-<environemnt>-sb-<name>-<random string>   | kebab-case         | a-z 0-9 -          | 6-50   | companycloud-acc-events-sb-mggbnkoe |
| Service Fabric Cluster       | <service short name>-<environment>-sfc                         | kebab-case         | a-z 0-9 -          | 4-23   | companycloud-acc-sfc                |
| Virtual Machine Scale Set    | <service short name>-<environment>-vmss                        | kebab-case         | a-z 0-9            | 3-61   | companycloud-acc-vmss               |
| Virtual Network (Vnet)       | <service short name>-<environment>-vnet                        | kebab-case         | a-z 0-9 - _ .      | 2-64   | companycloud-acc-vnet               |
| Subnet                       | <service short name>-<environment>-subnet<num>                 | kebab-case         | a-z 0-9 - _ .      | 2-64   | companycloud-acc-subnet1            |
| Network Security Group       | <service short name>-<environment>-nsg                         | kebab-case         | a-z 0-9 - _ .      | 2-64   | companycloud-acc-nsg                |
| Network Interface            | <service short name>-<environment>-<vminstancenumber>-nic<num> | kebab-case         | a-z 0-9 - _ .      | 2-64   | companycloud-acc-01-nic1            |
| Storage Container            | <service short name>-<environment>-<name>-sc                   | kebab-case         | a-z 0-9 -          | 3-63   | companycloud-acc-dsc-sc             |
| Web App                      | <service short name>-<environment>-<web app name>              | kebab-case         | a-z 0-9 -          | 1-60   | companycloud-acc-owa                |
| Function App                 | <service short name>-<environment>-<name>-func                 | kebab-case         | a-z 0-9 -          | 2-60   | companycloud-acc-updatepolicy-func  |
| Storage Account              | <service short name><role><randomstring>                       | lowercase          | a-z 0-9            | 3-24   | companycloudconfigmggbnkoe          |
| Virtual Machine (Windows)    | <role>-vm<number>                                              | kebab-case         | a-z 0-9 -          | 1-15   | fabric-vm01                       |
| Virtual Machine (Linux)      | <role>-vm<number>                                              | kebab-case         | a-z 0-9 -          | 1-64   | fabric-vm02                       |
| Blob                         | <name to identify blob>                                        | lowercase          | URL characters     | 1-1024 | /path/to/file.zip                 |
| Table                        | <name to identify table>                                       | lowercase          | a-z 0-9            | 3-63   | tenantdomain                      |
| Queue                        | <name to identify queue>                                       | kebab-case         | a-z 0-9 -          | 3-63   | policyservice-messages            |
| Network Security Group: Rule | <Allow/Deny><descriptive text>                                 | Pascal Case        | A-Z a-z 0-9 - _ .  | 1-80   | AllowSvcFabricClient              |
| Tag : Key                    | <description>                                                   | lowercase          | a-z 0-9            | 1-512  | environment                       |
| Tag: Value                   | <value>                                                        | case insensitive   | A-Z a-z 0-9        | 1-256  | production                        |
