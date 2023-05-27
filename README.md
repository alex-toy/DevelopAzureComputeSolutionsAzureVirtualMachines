# Develop Azure Compute Solutions - Azure Virtual Machines

## Windows machine

### Create an **Azure Virtual Machine**
<img src="/pictures/virtual_machine1.png" title="virtual machine"  width="800">
<img src="/pictures/virtual_machine2.png" title="virtual machine"  width="800">
<img src="/pictures/virtual_machine3.png" title="virtual machine"  width="800">


### Install IIS

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


### Deploying a .NET Core Web App to the server

- publish the app to the VM
<img src="/pictures/publish_app.png" title="publish app"  width="600">
<img src="/pictures/publish_app2.png" title="publish app"  width="600">
<img src="/pictures/publish_app3.png" title="publish app"  width="600">

You can see that there is an error because of the missing public IP address. In order to handle that issue, follow the below steps :

- on the VM, set the IP address as static

- add a DNS to the machine
<img src="/pictures/publish_app4.png" title="publish app"  width="900">

- add a rule for port 8122 to the *Network Security Group*
<img src="/pictures/publish_app5.png" title="publish app"  width="400">

- add the role of the *Management Service* on IIS on the VM

So far, you will still have an error

<img src="/pictures/publish_app6.png" title="publish app"  width="500">

Then you need to follow the below steps :

- on the VM, install the *ASP.NET Core 3.1 Hosting bundle*

- on the VM, install *Web Deploy v3.6 tool*

After all these steps, you can finally see the app deployed on the VM

<img src="/pictures/publish_app7.png" title="publish app"  width="900">


## Linux machine

### Create an **Azure Virtual Machine**
<img src="/pictures/linux_machine.png" title="linux virtual machine"  width="500">

Connect to the VM via Putty :

<img src="/pictures/linux_machine1.png" title="linux virtual machine"  width="500">

### Deploying ASP.NET Core Web App to the Linux VM

- Create ASP.NET Core Web App
<img src="/pictures/linux_project.png" title="linux virtual machine"  width="500">

- publish
<img src="/pictures/linux_publish.png" title="linux publish"  width="500">

This will generate a *publish* folder inside *.\LinuxVMApp\bin\Release\netcoreapp3.1*

- use *Winscp* to transfer the files to the Linux VM
<img src="/pictures/linux_publish2.png" title="linux publish"  width="500">

- drag and drop the *publish* folder to the home folder in the VM
<img src="/pictures/linux_publish3.png" title="linux publish"  width="900">

- inside the putty linux session run the commands in *linux_commands.txt*
<img src="/pictures/linux_publish4.png" title="linux publish"  width="900">

until the app is running

<img src="/pictures/linux_publish5.png" title="linux publish"  width="900">
