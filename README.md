# Develop Azure Compute Solutions - Azure Virtual Machines

## Create an **Azure Virtual Machine**
<img src="/pictures/virtual_machine1.png" title="virtual machine"  width="800">
<img src="/pictures/virtual_machine2.png" title="virtual machine"  width="800">
<img src="/pictures/virtual_machine3.png" title="virtual machine"  width="800">


## Install IIS

- Connect to that VM by RDP

- Inside **Server Manager**, do the following :
- choose **Add roles and features**
- choose **role-based or feature-based installation**
- add **Web Server IIS**
- continue with defaults and hit install
- open a browser in the VM and visit http://localhost/, you should see the default IIS site.


- In the VM portal, add an **Inbound Port Rule** allowing port 80.
<img src="/pictures/inbound_rule1.png" title="inbound port rule"  width="200">
<img src="/pictures/inbound_rule2.png" title="inbound port rule"  width="200">

- Open a browser and paste in the IP of the VM, you should see the IIS site.
<img src="/pictures/iis_site.png" title="IIS site"  width="600">


## Deploying a .NET Core Web App to the server

<img src="/pictures/iis_site.png" title="IIS site"  width="600">