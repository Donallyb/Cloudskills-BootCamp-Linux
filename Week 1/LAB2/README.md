# Lab 2: Manage Linux VMs with the Azure CLI

1. Create resource group
az group create --location northeurope --name cslinuxbootcamplab2
2. Create virtual machine
az vm create --resource-group csbootcamplinuxlab2 --name LinuxVM02 --image UbuntuLTS --admin-username azureuser --generate-ssh-keys
3. Connect to VM
ssh azureuser@13.69.182.249
4. Understand VM images
az vm image list --output table
az vm image list --offer UbuntuServer --all --output table
5. Understand VM sizes
az vm list-sizes --location northeurope --output table
6. VM power states
az vm get-instance-view --name LinuxVM02 --resource-group csbootcamplinuxlab2 --query instanceView.statuses[1] --output table
7. Management tasks
az vm list-ip-addresses --name LinuxVM02 --resource-group csbootcamplinuxlab2 --output table
az vm stop --name LinuxVM02 --resource-group csbootcamplinuxlab2
8. Clean-up Resources
az group delete --name csbootcamplinuxlab2

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-vm

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart