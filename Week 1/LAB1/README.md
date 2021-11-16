# Lab 1: Create a Linux virtual machine with the Azure CLI

1. Launch Azure Cloud Shell
2. Create a resource group
az group create --name csbootcamplinux --location northeurope
3. Create virtual machine
az vm create --resource-group csbootcamplinux --name LinuxVM01 --image UbuntuLTS --admin-username azureuser --generate-ssh-keys
4. Open port 80 for web traffic
az vm open-port --port 80 --resource-group csbootcamplinux --name LinuxVM01
5. Connect to virtual machine
ssh azureuser@40.127.173.112
6. Install web server
sudo apt-get -y update
sudo apt-get -y install nginx
7. View the web server in action
8. Clean-up Resources
az group delete --name csbootcamplinux

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-cli

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart