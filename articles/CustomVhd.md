# Using a custom VHD from Hyper-V for VM Image

When using a VHD from blob storage, during the deployment of the session host VMs, a resource type Image is created and will show up in the resource group to which the AVD deployed to.

## Virtual Machine Generation

When building an image in Hyper-V, the VM you are building the image from must be a Generation 1 VM. If it isn't the deployment will fail and the VMs that are built will have a boot issue present in the boot diagnostics.

## References

The references below contain information for building a VHD and ensuring it has the correct specifications as well as important settings to specify in the Windows Operating System.

[Prepare and customize a VHD image for Azure Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/set-up-customize-master-image)

[Prepare a Windows VHD or VHDX to upload to Azure](https://docs.microsoft.com/azure/virtual-machines/windows/prepare-for-upload-vhd-image)
