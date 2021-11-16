# Lab 4: Create and use an SSH public-private key pair for Linux VMs in Azure

1. Supported SSH key formats
2. Create an SSH key pair
ssh-keygen -m PEM -t rsa -b 4096
3. Provide an SSH public key when deploying a VM
az vm create --resource-group cslinuxbootcamplab4 --name linuxVM04 --image UbuntuLTS --admin-username azureuser --ssh-key-values laptop_rsa.pub
4. SSH into your VM
ssh azureuser@40.113.2.137
Welcome to Ubuntu 18.04.6 LTS (GNU/Linux 5.4.0-1063-azure x86_64)
5. Clean-up Resources
az group delete --name cslinuxbootcamplab4
### Notes:

Quickstart: SSH for Linux VMs
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/mac-create-ssh-keys

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart

