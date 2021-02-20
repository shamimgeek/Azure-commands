Lab - Script Extensions for Linux Virtual Machines - Resources
Lab - Script Extensions for Linux Virtual Machines - Resources
// Apply custom script extensions for a Linux Virtual Machine

az vm extension set --resource-group azuredemo --vm-name linuxvm --name customScript --publisher Microsoft.Azure.Extensions --settings customscript.json

This chapter has the configuration file attached as a resource. Please ensure you have a GitHub account and attach the URL for your account.

In the GitHub account , create a repository and add a file named install_web.sh1 that has the following contents

apt-get update -y && apt-get upgrade -y

apt-get install -y nginx

The following can be added to the customscript.json file. So create a file and add the following contents

{
  "fileUris": ["https://raw.githubusercontent.com/alashro/sampleweb/master/install_web.sh"],
  "commandToExecute": "./install_web.sh"
}
