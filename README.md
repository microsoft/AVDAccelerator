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

For a full AAD deployment, there are No prerequisites at this time.

## Additional Guides

- [Management and Logon Rights to VMs](articles/ManagementAndLogonRights.md)
- [Enable CAC Auth to AVD Accelerator Offering](articles/EnableCacAuth.md)
- [Using a custom VHD from Hyper-V for VM Image](articles/CustomVhd.md)
- [Creating Accounts During Deployment](articles/AccountCreation.md)
- [Resource Naming Convention](articles/NamingConvention.md)
- [Resources Deployed](articles/DeployedResources.md)

## Estimated Deployment Times

The following table provides example deployment time duration.
[Host Pool Sizing](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/virtual-machine-recs) calculations and [Type of workload](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/remote-desktop-workloads) are based off of general guidance and recommendations.

| Number of Concurrent Users | Host Pool Type | Number of Virtual Machines | Workload Type | Image | STIGs Applied | Deployment Time (mins) |
|--|--|--|--|--|--|--|
| 100 | Pooled | 4 |Medium | Windows 10 | Yes | 37 |
| 100 | Pooled | 4 | Medium | Windows 10/Office 365 | No | 21 |
| 250 | Pooled | 6 | Light | Windows 10 | Yes | 35 |
| 250 | Pooled | 6 | Light | Windows 10 | No | 21 |
| 500 | Pooled | 11 | Light | Windows 10/Office 365 | Yes | 38 |
| 500 | Pooled | 11 | Light | Windows 10 | No | 19 |
| 550 | Pooled | 12 | Light | Windows 10/Office 365 | Yes | 41 |
| 550 | Pooled | 12 | Light | Windows 10 | No | 22 |
| 50 | Personal | 50 | Standard DS1 v2 | Windows 10 /Office 365 | Yes | 49 |
| 50 | Personal | 50 | Standard DS1 v2 | Windows 10 /Office 365 | No | 25 |
| 98 | Personal | 98 | Standard DS1 v2 | Windows 10 /Office 365 | Yes | 51 |
| 98 | Personal | 98 | Standard DS1 v2 | Windows 10 | No | 21 |

Recommend to use simulation tools to test your deployment with both stress tests and real-life usage simulations.
Make sure your system is responsive and resilient enough to meet your needs.
