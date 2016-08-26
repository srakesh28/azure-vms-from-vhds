Azure Arm Templates IaaSv2 - Deploy 1 number of Windows VM's from custom VHD image with Data Disks

This Azure Arm Template deploys n number of Ubuntu VM's and assumes following is in place

Onetime steps:

1) Create a resource group, Storage account , vnet, and subnet created from UI or CLI

2) Create a Windows VM from Gallery  and customize it as you need, install everything that is required.

3) Follow this steps to capture this as image:

a) Note if it's SQL VM from Gallery you need to Sysprep at SQL Level also see steps here 
  https://msdn.microsoft.com/en-us/library/ee210664.aspx

b) Now Follow steps to sysprep at OS Level and Caputure Image :  http://www.codeisahighway.com/how-to-capture-your-own-custom-virtual-machine-image-under-azure-resource-manager-api/

4)) Once Image is captured it will be in your storage account in path as below (Get this path from UI of Storage Blob and leave image as is copy the URL) , you will see something like below

https://storageaccountname.blob.core.windows.net/system/Microsoft.Compute/Images/vhds/windows-image-name.vhd

Note its Critical : Image has to be in /system/Microsoft.Compute/Images/vhds/ in this path and in same storage account where you will create copies of new vms.
 

Now Use this template to deploy as many VM’s as you need.


ScreenShot
