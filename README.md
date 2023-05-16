<h1 align="center">Network File Shares and Permissions</h1>

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/fileshares.png" height="60%" width="45%"/>
</p>

<h1>Introduction</h1>
In this tutorial we will be creating and deploying a virtual machine within the Azure cloud environment. Microsoft Azure is a public cloud platform that offers a large collection of tools and computing services.


<h2>Tutorial Guideline</h2>


<h3>Step 1: Creating file shares with permissions</h3>

You should have your Domain Controller and Client VMs still up and running from the [previous tutorial](https://github.com/Mwajiduddin/Joining-a-client-to-a-domain-controller-virtual-machine-in-Azure) and we will start this tutorial in our Domain Controller virtual machine. Go to the C:\ drive and create these four folders: read access, write access, no access, and accounting; the folders are named based on their function.

Now we are going to set the permissions and to whom it will be shared to for each of these folders shown below:

| Folder:       | Group:         |  Permission: | 
| ------------- | -------------  |------------- |
| read access   | Domain Users   | Read         |
| write access  | Domain Users   | Read/Write   |
| no access     | Domain Admins  | Read/Write   |

We will come back to the accounting folder later in this tutorial.









