<p align="center"><img src="https://i.imgur.com/i6HiERh.png"/></p>


<h1>Azure Virtual Machines with Remote Desktop</h1>
This tutorial explains how to create a Resource Group and Virtual Machine in Microsoft Azure and access it via Remote Desktop. Following these steps, you can deploy and access a virtual machine in Azure using Remote Desktop Connection, which offers a graphical interface for remote VM management. This process involves carefully setting up network security settings and operating system configurations to guarantee accessibility and security.


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Active Azure Tenant and Subscription
- Remote Desktop Connection Software
- Basic Knowledge of Operating Systems (windows)
  

<h2>Steps to Deploy</h2>

<p align="center"><img src="https://i.imgur.com/o3U1IKP.png"/>
<img src="https://i.imgur.com/r4iWNOj.png"/></p>

You can use the Azure Portal to create a Virtual Machine. Once inside the portal, navigate to "Virtual machines" and select "Add" to start the creation process. 
The first thing we will do is actually go ahead and "create new" resource group. You can name this anything, but for the sake of this project, I chose to name mine RG-Azure-Portfolio. Then, I chose the VM portfolio name for my VM name. Now, it's time to configure it. 

<p align="center"><img src="https://i.imgur.com/vJ1ZE45.png"/>
<img src="https://i.imgur.com/2LYm1l7.png"/>
<img src="https://i.imgur.com/1W2Rtai.png"/></p>

Several different settings need to be configured. Some of those will include Region for locating the VM geographically,
availability options if high availability is needed, VM size (select based on CPU, RAM, and other needs), and choosing your operating system (Choose from available images like Windows Server or various Linux distributions). Then, you'll need to set up your administrator account by creating a username and password or SSH key for Linux VMs and opting in for the inbound ports since you will need an open TCP port 3389 to enable Remote Desktop access. And then to finish up with this page, make sure you check the Licensing box.

<p align="center"><img src="https://i.imgur.com/HOuTZzq.png"/>
<img src="https://i.imgur.com/44pKMiN.png"/></p>

You can go ahead and click "next" for the disc section and then "next" again for Networking. Here, you will see that it automatically creates our virtual Network, subnet, and Public IP address. A virtual network (VNet) and a subnet within Azure to ensure that the VM can communicate securely with other resources or the internet, if necessary. As for the public IP address, although it is not mandatory, it is needed if you want to access the VM from the internet via a Remote Desktop Connection. Then, you can make any needed changes or updates to the Network Security Group(NSG). An NSG defines security rules that allow or deny network traffic to the VM. As stated above, you'll need to allow inbound traffic on TCP port 3389 for remote desktop connection. Go ahead and click "review and create."

<img src="https://i.imgur.com/5xNxsDO.png"/></p>

Assuming everything looks good, you will see a message displaying "Validation Passed." You can now proceed to click "create" and your virtual machine deployment process will begin. It should only take a few minutes for our resource group, VM, and other resources to be created. Once it's finished and ready to go, we will copy the Virtual Machines public IP address and head over to the Remote Desktop Connection Client. You can search for "Remote Desktop Connection" in the Windows Start menu.

<p align="center"><img src="https://i.imgur.com/4hn19Hv.png"/>
<img src="https://i.imgur.com/IcjPMMo.png"/></p>

Once you open the Remote Desktop Client, click "add PC." Now, you can enter the public IP address of the VM you created. Then, you must specify the username and password set up during the virtual machine configuration. You will likely get a pop-up warning that the certificate cannot be verified. It will then ask you if you would like to proceed anyway. This is totally normal; you can go ahead and click "connect."

<p align="center"><img src="https://i.imgur.com/BM4ys7I.png"/></p>

You have successfully implemented all the steps required to create and configure a virtual machine in Azure and access it remotely. Once the VM is running, you'll need to configure the operating system. This includes: Setting up additional user accounts if multiple users need access, installing necessary software and updates to ensure the OS is up-to-date, and configuring system settings according to your requirements (like network, firewall settings, etc.). 

That's the end of this tutorial.
