# Enable CAC Auth to AVD Accelerator Offering

## Prerequisites

### Active Directory Federation Services (AD FS)

- AD FS needs to be accessible from the client connecting to the session hosts.
- AD FS needs to be configured for certificate based authentication
  - [Configure AD FS for user certificate authentication](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-user-certificate-authentication)

### Public Key Infrastructure (PKI)

- Session Hosts need to have a Remote Desktop Protocol (RDP) PKI certificate that can be verified from the client connecting to the session host.
- The Certificate Revocation List (CRL) or Online Certificate Status Protocol Responder (OCSP) for the RDP PKI certificate needs to be accessible from the client connecting to the session host.
  - Exposing the CRL server or OCSP responder man not be possible, you can upload them to blob storage in Azure and modify the published location on the Certificate Authority (CA) Server to point to the blob storage URL location.
- The CA certificate chain, root and intermediate CAs, need to be installed on the client establishing the connection to the session hosts.

### Remote Desktop Client

- The Windows Desktop client is the only client that supports Smartcard authentication
  - [Session host Authentication](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-user-certificate-authentication)
  - [Download the Windows Desktop Client](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-user-certificate-authentication)
- Using subscribe and entering your credentials may not use the correct feed url. Use the URL from the [list](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-user-certificate-authentication) and choose the option 'Subscribe with URL'.