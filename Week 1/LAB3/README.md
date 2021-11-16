# Lab 3: Manage Azure disks with the Azure CLI

1. Default Azure disks
2. Azure data disks
3. VM disk types
4. Launch Azure Cloud Shell
az vm create --resource-group csbootcamplinuxlab2 --name LinuxVM03 --image UbuntuLTS --admin-username azureuser --generate-ssh-keys --size Standard_DS2_v2 --data-disk-sizes-gb 64
5. Create and attach disks
az vm disk attach --resource-group csbootcamplinuxlab3 --vm-name LinuxVM03 --name myDataDisk --size-gb 128 --sku Premium_LRS --new
6. Prepare data disks
sudo fdisk -l used to identify disks
zureuser@LinuxVM03:~$ sudo parted /dev/sdd --script mklabel gpt mkpart xfspart xfs 0% 100%
azureuser@LinuxVM03:~$ sudo parted /dev/sdb --script mklabel gpt mkpart xfspart xfs 0% 100%
7. Take a disk snapshot
$osdiskid = (az vm show -g CSBOOTCAMPLINUXLAB3 -n LinuxVM03 --query "storageProfile.osDisk.managedDisk.id" -o tsv)
az snapshot create --resource-group CSBOOTCAMPLINUXLAB3 --source "$osdiskid" --name osDisk-backup16112021
az snapshot create --resource-group CSBOOTCAMPLINUXLAB3 --source $osdiskid --name osDisk-backup16112021 --copy-start false


### Notes:

Quickstart: Manage Azure disks
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-disks

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart