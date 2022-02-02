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

Azure Virtual Desktop (AVD) Accelerator is an Azure Marketplace offering to deploy AVD to your subscription with a consolidated User Interface (UI) for various deployment scenarios.

## Features

- Azure Active Directory (AAD) Virtual Machine (VM) Join
- On-Prem VM Join
- Apply DoD Security Technical Implementation Guides (STIGs) to deployed VMs using [PowerStig](https://github.com/Microsoft/PowerStig)
- Simplified VM sizing based on [Microsoft documentation](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/virtual-machine-recs)
- AAD Account creation

## Getting Started

Depending on the if the VMs are going to be AAD or On-Prem joined there are different prerequisites that are needed.

### Prerequisites

#### On-Prem VM Domain Join

- Accounts that will log into the VMs have to be synced to AAD.
- Connectivity to an On-Prem Domain Controller (Could be an Domain Controller as IAAS).
  - Virtual Network can be created during deployment or specify an existing one if an existing one it has to have the connectivity to the On-Prem domain.

#### Azure Active Directory VM Domain Join

At this time there are no prerequisites that exist if this is a full AAD deployment.

## Additional Guides

- [Management and Logon Rights to VMs](../articles/ManagementAndLogonRights.md)
- [Enable CAC Auth to AVD Accelerator Offering](../articles/EnableCacAuth.md)
- [Using a custom VHD from Hyper-V for VM Image](../articles/CustomVhd.md)

## Estimated Deployment Times
