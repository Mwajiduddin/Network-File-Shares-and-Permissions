<h1 align="center">Configuring network file shares and permissions</h1>

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/fileshares.png" height="60%" width="45%"/>
</p>

<h1>Introduction</h1>

In this tutorial we will be using both of our virtual machines from the [previous tutorial](https://github.com/Mwajiduddin/Joining-a-client-to-a-domain-controller-virtual-machine-in-Azure) to set up file shares and changing its permissions.


<h2>Tutorial Guidelines</h2>

<h3>Step 1: Creating file shares with permissions</h3>

You should have your Domain Controller and Client VMs still up and running from the [previous tutorial](https://github.com/Mwajiduddin/Joining-a-client-to-a-domain-controller-virtual-machine-in-Azure) and we will start this tutorial in our Domain Controller virtual machine. Go into the C:\ drive and create these four folders: read access, write access, no access, and accounting; the folders are named based on their function.

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d1.png" />
</p>

Now we are going to set the permissions and to whom it will be shared to for each of these folders shown below:

| Folder:       | Group:         |  Permission: | 
| ------------- | -------------  |------------- |
| read access   | Domain Users   | Read         |
| write access  | Domain Users   | Read/Write   |
| no access     | Domain Admins  | Read/Write   |

We will come back to the accounting folder later in this tutorial. To set the permission and shares, right click on the folder and select Properties, go to the "Sharing" tab, click on "Share", a window will appear where you will type in the Group name you want to view this folder then click on "Add". Change the folder permission by clicking on the black downward arrow underneath the "Permission Level" and selecting the proper permission then click "Share" and "Done." 

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d2.png" />
</p>

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d3.png" />
</p>

<h3>Step 2: Accessing folders as a normal client user</h3>

For this next step we need the network path where these folders are and this can be found by right clicking on one of the folders, selecting Properties, going into the Sharing tab, and underneath Network Path then copy the first two backslash and hostname. 

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d4.png" />
</p>


Then go to your Client VM and paste the path in File Explorer. 

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d5.png" />
</p>

You'll notice that you can't access the "no access" folder because only Admins are allow. You can access both the "read access" and the "write access" folder but you can't create anything in the "read access" folder.

<h3>Step 3: Obtaining access to the "accounting" folders as a normal client user</h3>

In your Domain Controller VM, go to Active Directory Users and Computers by searching it the Windows search bar, right click on your root domain name and create a new Organization Unit and name is "SECURITY GROUP." 

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d6.png" />
</p>

Create a new group inside "SECURITY GROUP" by right clicking, hover to "New" and selecting "Group." Name the group "ACCOUNTANTS" and press OK.

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d7.png" />
</p>

Now go to the "accounting" folder you made in your C:\ drive and share it "ACCOUNTANTS" and give it read/write access.

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d8.png" />
</p>

If we go back to our Client VM and try clicking on the accounting folder you'll see that we can't access yet, in order to gain access we need to make our user in the Client VM a member of ACCOUNTANTS in SECURITY GROUP. To do this we first need to know our user name for our Client VM which can be found by going into command prompt and typing in the command "whoami." 

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d9.png" />
</p>

Then go back to your Domain Controller VM, open ACCOUNTANTS in SECURITY GROUP, click on the "Members" tab, select "Add", type in your user in the box and click on "Check Names" and press OK.

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d10.png" />
</p>

Log out of the Client VM and log back in as the same user (remember from the previous tutorial that the password for the users is "Password1" when you try to log back in). Go to the "accounting" folder location and you'll see that you can finally open the folder. Once you're done with this lab remember to delete your resource group in Azure.

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/d11.png" />
</p>

