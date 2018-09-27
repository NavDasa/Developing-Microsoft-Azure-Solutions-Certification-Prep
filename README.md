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
