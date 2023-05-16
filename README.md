<h1 align="center">How to create a virtual machine in Microsoft Azure</h1>

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/dfwg.png" height="10%" width="25%" alt="Microsoft Azure Logo"/>
</p>

<h1>Introduction</h1>
In this tutorial we will be creating and deploying a virtual machine within the Azure cloud environment. Microsoft Azure is a public cloud platform that offers a large collection of tools and computing services.


<h2>Tutorial Guideline</h2>


<h3>Step 1: Creating a resource group</h3>

Log into your Microsoft Azure account (sign up if you don't have one) and type in "Resource Groups" in the top search bar. Click on the blue rectangular box labelled "Create resource group."

![search bar](https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a1.png)
![blue box](https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a2.png)

Type in what you want the name of your resource group to be, select a region, and then click on "Review + create." For this example, the name of my resource group is "VM-Lab1" and the region I selected to be in is "East US." 
After that you will be prompted by a validation page, just click "Create" at the bottom.

<p align="center">
  <img width="901" height="889" src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a3.png">
</p>

<p align="center">
  <img width="571" height="884" src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a4.png">
</p>

<h3>Step 2: Creating a virtual machine</h3>
Type and click on "Virtual machines" in the top search box. Click on the blue rectangular box labelled "Create" and select the first option "Azure virtual machine."

<p align="center">
  <img width="713" height="574" src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a5.png">
</p>



Right next to "Resource group" marked by the red asterick, select the name of the resource group that you previously made and then type in the name that you want your virtual machine to be. Select the same region that you chose for when making your resource group. So for this example, I named my virtual machine to be "VM1" and the region as "East US." Right next to "Image" select the operating system that you would like to run in your virtual machine. Then select the size that want your virtual machine to be, the higher the CPU, the better the VM's performance but the more costly it would be.

![vm selection](https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a6.png)

Under "Administrator account" you need to create a username and password in order to access the VM so make a note of it so that you won't forget. For the sake of easiness, I chose my username to be "VMuser1" and password as "WMpassword123." 

  >**Note**: *Do not follow this practice in the real world unless you want to be easily hacked.*

Under "Licensing" check box that states "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights." Then click "Review + create." 

![rc](https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a7.png)


<h3>Step 3: Logging into your virtual machine</h3>

Type and click on "Virtual machines" in the top search bar and you will see the virtual machine that you've made from the previous step. Click on it and you will see the configuration details of the virtual machine. The one that we're interested in is the VM's public IP address which will help us log into it. Copy the IP address by clicking on the "Copy to clipboard" icon.

![ip](https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a8.png)

Click on the Windows search bar, type and click on "Remote Desktop Connection." Next to "Computer" paste the VM's public IP address and click connect.

<p align="center">
  <img width="405" height="248" src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a9.png">
</p>

You will be prompted by window asking for credentials (the same credentials that you made under "Adminstrator account" from the previous step) so click on "More choices" and then click on "Use a different account." Type in the username and password that you created and click on OK. Then you will be prompted by another window stating that "The identity of the remote computer cannot be verified. Do you want to connect anyway?" click Yes.

<p align="center">
  <img width="444" height="465" src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a10.png">
</p>

<p align="center">
  <img width="389" height="397" src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a11.png">
</p>


As the virtual machine is booting you will see a screen about privacy settings for your device, just select no for each option and hit "Accept." There you have it, your own virtual machine!

![sc](https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/a12.png)

Lastly, once you're done creating and playing around with your virtual machine you need to delete the resource group(s) in Azure so that it won't charge you extra if you are not using it. So go into Azure, type in "Resource groups", click on the Resource group(s) shown, select "Delete resource group", copy the resource group's name and paste it below and then hit "Delete." Do this for each resource group and you're done!

<p align="center">
<img src="https://github.com/Mwajiduddin/Mwajiduddin/blob/main/images/b29.png" />
</p>
