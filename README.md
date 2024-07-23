We are deploying a simple web application on an Azure Virtual Machine, configuring the necessary network and security settings, and setting up monitoring and scaling.

Prerequisites:

An active Azure subscription
Basic knowledge of Azure Portal, Azure CLI, and web server configuration.

Steps:

Log in to Azure Portal: Navigate to Azure Portal.

Create a Resource Group:

Go to the "Resource groups" section.
Click "Add" and fill in the details (e.g., myResourceGroup).

Create a Virtual Machine:
Go to the "Virtual Machines" section.
Click "Add" and fill in the necessary details:
Subscription: Select your subscription.
Resource group: Select myResourceGroup.
Virtual machine name: myWebVM.

Region: Choose a suitable region.
Image: Select Ubuntu Server 20.04 LTS.

Size: Select an appropriate size (e.g., Standard_B1s for cost efficiency).

Authentication type: SSH public key.

Username: azureuser.

SSH public key: Paste your SSH public key.


Configure Networking:

Virtual network: Create a new virtual network or select an existing one.
Subnet: Default.
Public IP: Create a new public IP.
NIC network security group: Basic.
Inbound port rules: Allow SSH (port 22) and HTTP (port 80).
Review and Create: Review the settings and click "Create"


. Set Up the Web Server
Connect to the VM:

Use SSH to connect to the VM: ssh azureuser@<Public-IP>
Install Apache Web Server:

Update the package list: sudo apt update
Install Apache: sudo apt install apache2 -y
Start the Apache service: sudo systemctl start apache2
Enable Apache to start on boot: sudo systemctl enable apache2


Verify the Installation:

Open a web browser and navigate to http://<Public-IP>. You should see the default Apache welcome page.

