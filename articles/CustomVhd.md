# Using a custom VHD from Hyper-V for VM Image

When using a VHD from blob storage, during the deployment of the session host VMs a resource type Image is created and will show up in the resource group the AVD deployment deployed to.

## Virtual Machine Generation

When building an image in Hyper-V the VM you are building the image from has to be a Generation 1 VM. If not the deployment will fail and the VMs that are built will have a boot issue when looking at the boot diagnostics.

## References

These are references for building a VHD and ensuring it has the correct specifications plus important settings to set in the Windows Operating System.

[Prepare and customize a VHD image for Azure Virtual Desktop](https://docs.microsoft.com/en-us/azure/virtual-desktop/set-up-customize-master-image)

[Prepare a Windows VHD or VHDX to upload to Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/prepare-for-upload-vhd-image)
