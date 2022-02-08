# Resources Deployed

The following resources are deployed during the Azure Virtual Desktop Accelerator. Some resources do not deploy and are dependent on a condition.

|Resource |Instances |Condition |
--- | --- | --- |
Virtual Machine | Number of VMs Deployed | |
Network Interface |  Number of VMs Deployed | |
Disk (OS Disk) |  Number of VMs Deployed | |
Virtual Network | 1 | If deployment is not On-Prem and an existing one is used |
Network Security Group | 1 | If deployment is not On-Prem and an existing one is used |
Host Pool | 1 | |
Workspace | 1 | |
Application Group | 1 | |
Key Vault | 1 | User Accounts are created during deployment |
Custom Script Extension | 1 | STIGs are applied |
Microsoft Powershell DSC | 1 | STIGs are applied |
VM Sizing Deployment Script | 1 | |
Directory Management Deployment Script | 1 | |
Account Creation Deployment Script | 1 | Azure AD Accounts are created |
