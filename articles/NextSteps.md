# Next Steps

After a deployment using the AVD Accelerator, here are recommended next steps to further enhance your Azure Virtual Desktop experience.

## Profile Management

FSLogix is a set of solutions that enhance, enable, and simplify non-persistent Windows computing environments.

Azure Virtual Desktop offers FSLogix profile containers as the recommended user profile solution. FSLogix is designed to roam profiles in remote computing environments, such as Azure Virtual Desktop. At sign-in, this container is dynamically attached to the computing environment using a natively supported Virtual Hard Disk (VHD) and a Hyper-V Virtual Hard Disk (VHDX). The user profile is immediately available and appears in the system exactly like a native user profile.

For more information about implementing FSLogix, please reference the following articles:

- [What is FSLogix?](https://docs.microsoft.com/fslogix/overview)
- [FSLogix for the enterprise](https://docs.microsoft.com/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix)
- [Create a profile container with Azure Files and Azure AD DS](https://docs.microsoft.com/azure/virtual-desktop/create-profile-container-adds)
- [Create a profile container with Azure Files and AD DS](https://docs.microsoft.com/azure/virtual-desktop/create-file-share)
- [Create a profile container with Azure Files and Azure Active Directory](https://docs.microsoft.com/azure/virtual-desktop/create-profile-container-azure-ad)

## Monitoring

Set up monitoring for AVD using Azure native services with Azure Monitor and Log Analytics.

- [Use Azure Monitor for Azure Virtual Desktop to monitor your deployment](https://docs.microsoft.com/azure/virtual-desktop/azure-monitor)

## Autoscale

To optimize deployment costs or running session hosts, there are methods to automate scaling, which refers to shutting down and deallocating session host VMs during off-peak usage hours, then turning them back on and reallocating them during peak hours. Options include using Autoscale, currently in preview, as well as leveraging Azure Automation.  For more information, please reference the resources below:

- [Autoscale (preview) for Azure Virtual Desktop host pools](https://docs.microsoft.com/azure/virtual-desktop/autoscale-scaling-plan)
- [Scale session hosts using Azure Automation](https://docs.microsoft.com/azure/virtual-desktop/set-up-scaling-script)

## Additional Resources

- [Security best practices](https://docs.microsoft.com/azure/virtual-desktop/security-guide)
