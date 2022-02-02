# Azure Virtual Desktop (AVD) Accelerator

## Overview

Azure Virtual Desktop (AVD) Accelerator is an Azure Marketplace offering to deploy AVD to your subscription with a consolidated User Interface (UI) for various deployment scenarios.

### Features

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

### Management and Logon Rights to VMs

#### Administrator Access to VMs

There is a group created when using the AVD Accelerator, 'sg-{ProjectName}-avdadmin', that assigns Azure role (Virtual Machine Administrator Login) needed to login to the VM and the assignment to the Application Group. This allows these users to login to the VM with Administrator rights.

#### User Logon Rights to VMs

There is a group created when using the AVD Accelerator, 'sg-{projectName}-avd', that assigns the Azure role (Virtual Machine User Login) needed to login to the VM and the assignment to the Application Group. This allows the users to login to the VMs as a User.

## Estimated Deployment Times

## Enable CAC Auth to AVD Accelerator Offering

### Prerequisites

#### Active Directory Federation Services (AD FS)

- AD FS needs to be accessible from the client connecting to the session hosts.
- AD FS needs to be configured for certificate based authentication
  - [Configure AD FS for user certificate authentication](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-user-certificate-authentication)

#### Public Key Infrastructure (PKI)

- Session Hosts need to have a Remote Desktop Protocol (RDP) PKI certificate that can be verified from the client connecting to the session host.
- The Certificate Revocation List (CRL) or Online Certificate Status Protocol Responder (OCSP) for the RDP PKI certificate needs to be accessible from the client connecting to the session host.
  - Exposing the CRL server or OCSP responder man not be possible, you can upload them to blob storage in Azure and modify the published location on the Certificate Authority (CA) Server to point to the blob storage URL location.
- The CA certificate chain, root and intermediate CAs, need to be installed on the client establishing the connection to the session hosts.

#### Remote Desktop Client

- The Windows Desktop client is the only client that supports Smartcard authentication
  - [Session host Authentication](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-user-certificate-authentication)
  - [Download the Windows Desktop Client](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-user-certificate-authentication)
- Using subscribe and entering your credentials may not use the correct feed url. Use the URL from the [list](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-user-certificate-authentication) and choose the option 'Subscribe with URL'.

## Using a custom VHD from Hyper-V for VM Image

When using a VHD from blob storage, during the deployment of the session host VMs a resource type Image is created and will show up in the resource group the AVD deployment deployed to.

### Virtual Machine Generation

When building an image in Hyper-V the VM you are building the image from has to be a Generation 1 VM. If not the deployment will fail and the VMs that are built will have a boot issue when looking at the boot diagnostics.

### References

These are references for building a VHD and ensuring it has the correct specifications plus important settings to set in the Windows Operating System.

[Prepare and customize a VHD image for Azure Virtual Desktop](https://docs.microsoft.com/en-us/azure/virtual-desktop/set-up-customize-master-image)

[Prepare a Windows VHD or VHDX to upload to Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/prepare-for-upload-vhd-image)