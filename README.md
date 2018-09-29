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

# Funtions
Create an App Service Plan to Host a Web App:

In this lesson, we create an app service plan and review the different type of app service plan offerings.

Create a Web App Using the Portal:

n this lesson, we create a Web App within our App Service Plan. This Web App is an environment within the App Service Plan which runs a raw web application such as an ASP.NET MVC application. This environment provides features such as (amongst many more):

Deployment slots
Continuous integration
Load balancing
Automatic scaling.

Use Visual Studio to Create and Deploy an ASP.NET Application to a Web App:

In this lesson, we create an ASP.NET MVC application with Visual Studio and deploy it to our Azure Web App.

Add Tracing and Monitor Performance:

In this lesson, we add Application Insights and tracing capabilities to our web application.

Create a Function App:

In this lesson, we create a functions app which provides an execution environment for one or more functions. We also examine several of the properties of a function app.

Create a Function Triggered by a Timer:

In this lesson, we create an Azure Function that runs on a regular basis by using a timer trigger.

Manage and Monitor a Function:

In this lesson, we examine how an Azure Function can be monitored from within the portal.

Delete a Function:

In this lesson, we delete an Azure Function.

Create a Function Triggered by a WebHook:

In this lesson, we create an Azure Function that is executed by a WebHook.

Create a Function Triggered by a blob event:

In this lesson, we create a function that is triggered when a new blob is created.

Integrate a Function with a Storage Queue:

In this lesson, we create an Azure Function that is executed every time a message is placed within a storage account queue.

Create and Deploy a Function App with Visual Studio:

In this lesson, we develop functions from within Visual Studio. We then deploy a function app from Visual Studio to Azure. Finally, we run and debug azure functions on our local development system.

Understand and Use Function Proxies:

In this lesson, we learn to create Azure Function Proxies.

Integrate Functions with Event Grid:

In this lesson, we examine Event Grid and how it can be used to route events to Azure Functions.

Create Understand WebJobs:

In this lesson, we implement a WebJob project that responds to Storage Account queue messages and also to blob creation events.

Design Azure App Service API Apps:

Create an API App Service Plan:

we create an App Service Plan to host a Web API application.

Create and Deploy an API App That Uses Swagger and Swashbuckle: (OpenAPI):

In this lesson, we create an ASP.NET Web API application in Visual Studio and examine how to use Swagger/Swashbuckle to expose and document the API.

Deploy an API App from Visual Studio:

we deploy our Web API from Visual Studio to our Azure App Service.

# Implement API Management:

we create an API Management Service.

Create a Product with an API:

In this lesson, we create an API management product. We then create a managed API which fronts an external web service on the Internet. Finally, we associate the API with the product and expose it to developers.

Enable Developer Access: (Also add a new user and give access to the API):

we enable access to our API to developers.

Create Policies to Modify Input and Output: 

we create API Management policies to control access to our API and also modify the format of output data.

Inboud Processing: Allow (we getError)and Forbid (We won't get Error)
OutBound Processing: Convert the out XML into JSON.

Configure Rate Limits:

In this lesson, we learn about using policies on our API to control the rate of calling of the API as well as how much data can be moved through the API.  You can see the video at this point of time to get the police, how its working. we can also set in millions and the number of requests.

Configure Caching:

In this lesson, we configure policies to check requests for matches in an output data cache, and also to associate result data with a request and place that data within the cache. (Inbond paramenter: Get from cache, Out bound parameter: Store to cache)

Inbound: <cache-lookup vary-by-developer="false" vary-by-developer-groups="false">
            <vary-by-query-parameter>a,b</vary-by-query-parameter>
         </cache-lookup>
outbound: <cache-store duration="3600" />

Manage API Versions:

we examine versioning and running multiple versions of our API.

Customize Publisher and Developer Portals:

In this lesson, we examine the publisher and developer portals. We take a quick spin around the publisher portal and then cover how you can change styles and upload custom content in the developer portal.

Integrate with Git:

we learn to utilize Git to version control our APIs.

# Develop Azure App Service Logic Apps

Managed services in azure,In side of app service environment, 300 different data types events.

Create a Logic App Service with the Portal:

we create a Logic App to host one or more workflows.

Implement a Logic App That Responds to Storage Queue Messages:

we create a Logic App workflow that is triggered by the arrival of messages in a storage account queue.

# Mobile APPS:

Create a Mobile App Service with the Portal:

we create a Mobile App Service in Azure. This App Service will form the underpinnings of our mobile application, its data storage, and authorization schemes.

Create a Mobile Client Using the Microsoft Mobile SDK for Xamarin.iOS:

we create an iOS application using Xamarin that will utilize our Mobile App Service.

Add Offline Sync to the Mobile Client:

we add offline caching capabilities to the mobile client.

Add Google Authentication to the Mobile App Service: We can see how we can get Client ID and Client seceret.

we configure the backend app service to support Google authentication.

Add Google Authentication to the Xamarin.iOS mobile client:

Add Google Authentication to the Xamarin.iOS mobile client.

# Service fabric:

Clustering technology, Standerd WCF Applications, Openshift, Cloud foundry, Automatic scaling, manage clusters, availabity sets, fault and update domains, Microservices, Automatic data persistent, Version control, automatic upgrages. 

Creating a Service Fabric Cluster with the Portal:

In this lesson, we create a service fabric cluster using the portal and examine several of its important characteristics.

Create an Azure Service Fabric App:

In this lesson, we examine a sample Service Fabric stateless service application. We review the coding patterns that are utilized and required for the exam.
 
Deploy a Service Fabric Application from Visual Studio:

In this lesson, we deploy our service fabric application from visual studio to our service fabric cluster. We then examine its deployment and give it a run in Azure.

# Design and implement third-party Platform-as-a-Service (PaaS):

Leverage Azure Marketplace Solutions and Services:

In this lesson, we cover how third-parties can offer services in the Azure Marketplace, including the various pricing models available. We close with pointing you to where you can find how to make your own offerings.

Provision Applications Using Azure Quick-Start Templates:

we take a look at the Azure quick-start templates available on Github and where you can find information on contributing.

Create Managed Azure Applications:

we learn about Azure Managed Applications and create/deploy a sample managed application.

Implement Docker Swarm Applications:

we create a docker swarm application using Azure Container Service (ACS). In this lesson it also describes that how to create a docker swarm cluster within the az - cli, and how to connect to the master (cluster) and deploy a docker stack voting app in the cluster. 
