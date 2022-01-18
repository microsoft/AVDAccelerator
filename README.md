# Azure Virtual Desktop (AVD) Accelerator

## Overview

Azure Virtual Desktop (AVD) Accelerator is an Azure Marketplace offering to deploy AVD to your subscription with a consolidated User Interface (UI) for various deployment scenarios.

### Features

- Azure Active Directory (AAD) Virtual Machine (VM) Join
- On-Prem VM Join
- Apply STIGs to deployed VMs
- Simplified VM sizing based on Microsoft documentation
- AAD Account creation

## Getting Started

Depending on the if the VMs are going to be AAD or On-Prem joined there are differnt prerequisites that are needed.

### Prerequisites

#### On-Prem VM Domain Join

- Accounts that will log into the VMs have to be synced to AAD.
- Connectivity to an On-Prem Domain Controller (Could be an Domain Controller as IAAS).
  - Virtual Network can be created during deployment or specify an existing one if an existing one it has to have the connectivity to the On-Prem domain.

#### Azure Active Directory VM Domain Join

At this time there are no prerequistes that exist if this is a full AAD deployment.

### Management and Logon Rights to VMs

#### Administrator Access to VMs

There is a group created when using the AVD Accelerator, 'sg-{ProjectName}-avdadmin', that assigns Azure role (Virtual Machine Administrator Login) needed to login to the VM and the assignment to the Application Group. This allows these users to login to the VM with Administrator rights.

#### User Logon Rights to VMs

There is a group created when using the AVD Accelerator, 'sg-{projectName}-avd', that assigns the Azure role (Virtual Machine User Login) needed to login to the VM and the assignment to the Application Group. This allows the users to login to the VMs as a User.

## Estimated Deployment Times

## Enable CAC Auth to AVD Accelerator Offering
