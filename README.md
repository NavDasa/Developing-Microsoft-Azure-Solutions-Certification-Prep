# Developing-Microsoft-Azure-Solutions-Certification-Prep
Developing Microsoft Azure Solutions Certification Prep

# Identify Supported Workloads
In this lesson, we go over the concept of a workload, which describes the nature of a solution that can be run with virtual machines.
Facets of workflows that we will cover are:

What is a workload?
What are characteristics of a workload?
How can you identify an azure suitable workload?

Azure Virtual Machine Architecture:

We will be working extensively with VMs, so in this lesson, we cover some of the components of an Azure VM and network architecture; including public IP addresses, network interface controllers, network security groups, virtual networks, subnets, disk drives and diagnostics.

Create a Linux VM:

In this lesson, we use the Azure portal to create a Linux VM (Ubuntu). We also SSH into the VM, install Apache, and then access the website from the Internet.

1. How the linux server running Apache2 Server, in the Azure VM service, also changing the Networking inbound rules.

Create and Use Images from Windows and Linux Virtual Machines:

In this lesson, we learn to create images of both Windows and Linux VMs, and then how to launch new VMs from those images. These images preserve the state of the installed software and can be used to redeploy custom solutions without having to reconfigure the installed software.

Deploy Workloads with Terraform:

In this lesson, we learn how to use Terraform to deploy an Azure VM. During this process, we will use the Cloud Shell and examine two Terraform files: one to create a resource group, and one to create a VM including its virtual network infrastructure. During this process, we work with the init - plan - apply terraform pattern and create the resources.

 Deploy Workloads with Ansible:
 
In this lesson, we learn how to use Ansible to deploy an Azure VM. During this process, we will use the Cloud Shell and examine a simple Ansible playbook which creates a VM, and we'll also have Ansible create that VM. We also learn two Azure CLI commands to create a resource group and virtual network.

Configure a VM with the Custom Script Extension (CSE):

we use the VM Agent to install the Custom Script Extension. Then using CSE, we execute a simple script on the VM to create a file.

Configure a VM with Powershell Desired State Configuration (DSC):

Configure an Azure VM with WebDeploy and Powershell DSC:

In this lesson, we continue with DSC and use it to configure a Windows web server with WebDeploy installed. This will enable the web server to have applications deployed to it from remote tools such as Visual Studio.

Create and Deploy an ASP.NET Application to an Azure VM from Visual Studio:

In this lesson, we create a web application with Visual Studio and deploy that app to the Azure VM. To accomplish this, we use the integrated deploy tools in Visual Studio.

Remote Debug a Web App on an Azure VM:
 
 In this lesson, we use Visual Studio to configure remote debugging on an Azure VM. Once configured, we examine the configuration changes made, connect to the IIS process, and remotely debug the application.
 
# VMSS
Scale-up a VM:

In this lesson, we examine how to scale up an Azure virtual machine. This process is referred to as vertical scaling, and we use the portal to scale up a VM.

Scale-up of a virtual mechine means increasing the CPU and RAM of the Particular VM.

Just go to the Disk and change choose the upper one and resize, at that time there will be a down time of server.

Note: There is No feature in Azure to automatically Scale down and scale up. We should analyze some metrics, and write automation scripts for that metrics. 

# Create a VM Scale Set (VMSS):

In this lesson, we create a virtual machine scale set (VMSS). A VMSS is Azure’s integrated service for managing scale-out, also known as horizontal scaling.

Configure VMSS Scale-out:

In this lesson, we configure a VMSS to scale-out when the aggregate utilization of its virtual machines CPU's exceeds 70%.

Note: The public IP will be allocated to load balancer of the instance.

Force a VMSS Scale-out:

In this lesson, we force the scale-out of our VMSS by running a script on one of the web servers that maximized the CPU.

Note: In VMSS you need to connect to by the DNS name by giving port number example myvmss.westus.cloudapp.azure.com:50000 and also Enter Username and password to connect to the VMSS. In this leasson, as we set up the autoscalling, but we don't know how it works, so in order to know we are login to the mechine and increasing the load and then it will automatically scale - out the new instance. 

For CPU Stress on VMSS:
Run the below commands to make sure the utilization is more:

Invoke-WebRequest -Uri https://raw.githubusercontent.com/linuxacademy/content-azure-70532/master/scripts/CpuStress.psm1 -OutFile CpuStress.psm1

Import-Module .\CpuStress.psm1

New-CpuStress 4

Note: In newer version of azure there is an ability to assign an public - ip address for a VMSS. we can remote into those directly instead of dooing dns. But it is not by default we can also configure it through power shell or ARM Templetes.

Force a VMSS Scale-in: 

We need to set up a new rule of scale-in, We have a problem that even when the cpu is down then the 70% there will be the same rule and VMSS instances will be two only, So that is the problem So, we need to write a Scale-In Rule, So in this leasson they will close the work load and off the Job then the automatically scale-in rule will drops down to 1 VM from 2.

Command: Get-CpuStress | Stop-CpuStress

Implement Accelerated Networking:

Accelerated Networking means simply noting but 
With Accelerated Networking: Virtual Switch + Network card.
Without Accelerated Networing: Network card.

In this lesson, we examine Accelerated Networking and how to configure your Azure VMs to utilize this service which can get you up to 30Gbps throughput between servers on your Azure VNet's.

Configure Disk Caching and Add/Remove Data Disks:

In this lesson, we examine disk caching and also how to attach and detach data disks from a VM.

Note: Even if you delate the VM, the data disk won't be delated and will be longer life.

Plan Storage Capacity:

In this lesson, we cover the limitations of disks on VMs and discuss the means of planning disk size and performance for a VM.

Configuring Shared Files with Azure Files:

In this lesson, we learn about Azure Files, a managed service for sharing files using the SMB protocol. During the lesson, we create an Azure File Share which will later be mounted to both a Windows and Linux VM(s).

Mount an Azure File Share on a Windows and Linux VM:

In this lesson, we mount the file share created in the previous lesson to a Windows and a Linux VM. We then create content (files) which can be seen from both systems.

Understand Azure Storage Account Replication:

In this lesson, we discuss the types of data replication available in Azure: LRS, ZRS, GRS and RA-GRS.

Contrast Standard/Premium Storage and Managed/Unmanaged Disks:

In this lesson, we discuss the differences between standard and premium storage, as well as between managed(can be used in SSD, disk in IOPS, scalability, storage accounts, control of overaall performance, snapshot at solid state, saving money, GRS replicated,) and unmanaged disks( how much you used you can pay that much, transaction charge, high performace).

Understand VM Disk Encryption:

In this lesson, we quickly go over the concepts you need to know relative to performing disk encryption that may be on the exam.

Windows uses Bit locaker, and linux uses DM-Crpt. keys used in key vault.

Implement StorSimple:

In this lesson, we quickly examine StorSimple and what it has to offer in the areas of storage consolidation.

Storage Infrasturance, for on-premises storage, backups, disaster recovery, backup copies, pysical, and virtual servers connected. Schecudeled, backups.

Implement Azure File Sync:

In this lesson, we quickly go over Azure File Sync and what it has to offer in terms of replicating files into Azure File Storage.

On-premises sync upto the Azure, Files locally can be synced into azure. Multi-Master sync storage. Don't work on Azure files in between regions.

