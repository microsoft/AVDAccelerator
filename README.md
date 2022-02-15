# Azure Virtual Desktop (AVD) Accelerator

- [Azure Virtual Desktop (AVD) Accelerator](#azure-virtual-desktop-avd-accelerator)
  - [Overview](#overview)
  - [Features](#features)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
      - [On-Prem VM Domain Join](#on-prem-vm-domain-join)
      - [Azure Active Directory VM Domain Join](#azure-active-directory-vm-domain-join)
  - [Additional Guides](#additional-guides)
  - [Estimated Deployment Times](#estimated-deployment-times)

## Overview

Azure Virtual Desktop (AVD) Accelerator is an Azure Marketplace offering that allows you to use your existing subscription to deploy a customized AVD environment. An easy-to-follow setup wizard will guide you through the process to deploy AVD according to your needs.

## Features

- Azure Active Directory (AAD) Virtual Machine (VM) Join
- On-Prem VM Join
- Apply DoD Security Technical Implementation Guides (STIGs) to deployed VMs using [PowerStig](https://github.com/Microsoft/PowerStig)
- Simplified VM sizing based on [Microsoft documentation](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/virtual-machine-recs)
- AAD Account creation

## Getting Started

Prerequisites vary based on whether the VMs are going to be On-Prem or AAD joined.

### Prerequisites

#### On-Prem VM Domain Join

- Accounts that will log into the VMs must be synced to Azure Active Directory (AAD).
- Connectivity to an On-Prem Domain Controller (could be a Domain Controller as IAAS).
  - A Virtual Network can be created during deployment or an existing one be specified if it has connectivity to the On-Prem domain.

#### Azure Active Directory VM Domain Join

For a full AAD deployment, there are no prerequisites at this time.

## Additional Guides

- [Management and Logon Rights to VMs](articles/ManagementAndLogonRights.md)
- [Enable CAC Auth to AVD Accelerator Offering](articles/EnableCacAuth.md)
- [Using a custom VHD from Hyper-V for VM Image](articles/CustomVhd.md)
- [Creating Accounts During Deployment](articles/AccountCreation.md)
- [Resource Naming Convention](articles/NamingConvention.md)
- [Resources Deployed](articles/DeployedResources.md)

## Estimated Deployment Times

The following table provides example deployment time duration. Host Pool Sizing calculations and Type of workload are based on recommendations found @ <https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/virtual-machine-recs> and <https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/remote-desktop-workloads>. 

|Test |Host Pool Sizing |Pooled-Personal |Amount of VMs created |Type of Workload |Image |STIG'd |Duration (mins) |
--- | --- | --- |--- | --- | --- |--- |
1 | 100 | pooled | 4 med | win10 | yes | 37 |
2 | 100 | pooled | 4 med | win10/356 | no | 21 |
3 | 250 | pooled | 6 light | win10 | yes | 35 |
4 | 250 | pooled | 6 light | win10 | no | 21 |
5 | 500 | pooled | 11 light | win10/356 | yes | 38 |
6 | 500 | pooled | 11 light | win10 | no | 19 |
7 | 550 | pooled | 12 light | win10/365 | yes | 41 |
8 | 550 | pooled | 12 light | win10 | no | 22 |
9 | 50 | personal | 50 | 1x Standard DS1 v2, 1 vcpu | win10 /365 | yes | 49 |
10 | 50 | personal | 50 | 1x Standard DS1 v2, 1 vcpu | win10 /365 | no | 25 |
11 | 98 | personal | 98 | 1x Standard DS1 v2, 1 vcpu | win10 /365 | yes | 51 |
12 | 98 | personal | 98 | 1x Standard DS1 v2, 1 vcpu | win10 | no | 21 |

Recommend to use simulation tools to test your deployment with both stress tests and real-life usage simulations. Make sure your system is responsive and resilient enough to meet your needs. Note - review your subscription limits when creating host pools. <https://docs.microsoft.com/en-us/azure/virtual-desktop/troubleshoot-set-up-issues#error-exceeding-quota-limit>
