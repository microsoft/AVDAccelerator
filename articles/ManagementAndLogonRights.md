# Management and Logon Rights to VMs

## Administrator Access to VMs

There is a group created when using the AVD Accelerator, 'sg-{ProjectName}-avdadmin', that assigns Azure role (Virtual Machine Administrator Login) needed to login to the VM and the assignment to the Application Group. This allows these users to login to the VM with Administrator rights.

## User Logon Rights to VMs

There is a group created when using the AVD Accelerator, 'sg-{projectName}-avd', that assigns the Azure role (Virtual Machine User Login) needed to login to the VM and the assignment to the Application Group. This allows the users to login to the VMs as a User.