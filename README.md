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
