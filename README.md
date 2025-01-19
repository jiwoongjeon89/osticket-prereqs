<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1: Azure Virtual Machine
- Item 2: osTicket
- Item 3: Dependency files for osTicket

<h2>Installation Steps</h2>

In this lab, I will demonstrate how to install osTicket from scratch using a windows virtual machine in Azure.  
<p>
<img width="2672" alt="1" src="https://github.com/user-attachments/assets/71388368-d998-40d2-9266-b8cfdc59d491" />
</p>
<p>
I will first create a Windows 10 virtual machine on Azure. 
</p>
<br />

<p>
<img width="1282" alt="2" src="https://github.com/user-attachments/assets/5dcd6c41-5693-4b0b-b482-4000c0343d10" />
</p>
<p>
I am now opening Windows App to run the virtual machine on my MacBook.  
</p>
<br />

<p>
<img width="1121" alt="4" src="https://github.com/user-attachments/assets/d4b3cbc4-dd68-4ea4-915f-c09723f5bfdc" />

</p>
<p>
I am in my virtual machine and before we install osTicket, we need to install and enable IIS in Windows with CGI. 
  <p>
To do this, we need to go to ‘Control Panel > Programs > Programs and Features > Turn Windows features On and Off’. 
  </p>
  <p>
   Then check the box next to Internet Information Services. 
  </p>
  We also need to check the box of CGI which is under ‘World Wide Web Services > Application Development Features’ 
</p>
<br />

<p>
  <img width="1124" alt="3" src="https://github.com/user-attachments/assets/ac233253-0321-4599-ad95-919184997c97" />
  </p>
  <p>
I will be downloading osTicket and some of the dependency files that osTicket needs. 
</p>

<br />

<p>
  <img width="498" alt="5" src="https://github.com/user-attachments/assets/708a031f-10f9-43b8-8227-62591566a2bd" />
</p>
<p>
I will start by installing PHP Manager.

</p>
<br />

<p>
  <img width="498" alt="6" src="https://github.com/user-attachments/assets/6910ef0d-8a20-4f4d-adc0-c821ab7e076c" />
</p>
<p>
  Then, install Rewrite Module 
  
</p>
<br />

<p>
  <img width="1116" alt="7" src="https://github.com/user-attachments/assets/50e047a4-7ea8-456a-9923-fb1bc0777a08" />
</p>
<p>
  For later use, we will make a PHP folder in the C drive and unzip PHP 7.3.8 into the “C:\PHP” folder 
 
</p>
 <br />
 
<p>
  <img width="476" alt="8" src="https://github.com/user-attachments/assets/cbea5067-4e71-4919-91d8-a1406f281850" />
</p>
<p>
  Then, install VC_redist.x86.exe. 

</p>
  <br />
  
<p>
  <img width="491" alt="9" src="https://github.com/user-attachments/assets/1b4dd0b1-209b-4d6c-bce9-b571d29f7e1c" />
</p>
<p>
  And install MySQL 5.5.62 
  
</p>
<br />

<p>
  <img width="1901" alt="10" src="https://github.com/user-attachments/assets/874f845e-49ec-4d02-930a-cb714ec1c97d" />
<img width="1901" alt="11" src="https://github.com/user-attachments/assets/60c51add-1c5c-4f6c-8230-ecfa7e7c9f77" />
</p>
<p>
  Now I will register PHP from within IIS through these steps: Open the IIS as Admin > PHP Manager > Register new PHP version > Browse to the PHP file we made earlier. 
  Then we will reload the IIS. 
 
</p>
 <br />
 
<p>
  <img width="1122" alt="12" src="https://github.com/user-attachments/assets/59d2297e-eb96-440f-9192-56d65bde6c77" />
</p>
<p>
  Now, extract the osTicket folder which will have a "script" file and an "upload" file. 

</p>
<br />

<p>
  <img width="1123" alt="13" src="https://github.com/user-attachments/assets/89f42d49-5ae2-43e8-afbb-3d558e890864" />
</p>
<p>
  We will copy the “upload” folder into “c:\inetpub\wwwroot” Then rename the "upload" folder to “osTicket”. 
  
</p>
<br />

<p>
  <img width="1902" alt="14" src="https://github.com/user-attachments/assets/dcc8889f-9872-42b5-a85a-fe4b32923e83" />
</p>
<p>
  Reload the IIS again. 
  
</p>
<br />

<p>
  <img width="1901" alt="15" src="https://github.com/user-attachments/assets/3862762e-1761-4b99-8dae-b2e73ca3ccdd" />
</p>
<p>
  Now we will open the osTicket site in the IIS by going to Sites > Default Web Sites > Browse *:80(http) 
  
</p>
<br />

<p>
  <img width="1426" alt="16" src="https://github.com/user-attachments/assets/81bf8c5e-15b9-4093-8580-8ba238b8ce8a" />
</p>
<p>
  This is what the site will look like.

</p>
<br />

<p>
  <img width="1118" alt="17" src="https://github.com/user-attachments/assets/8edb326b-2eb3-4283-849a-16ad359fe338" />
</p>
<p>
  Now we will rename a file on the hard drive that osTicket uses to make configurations.  
</p>
<p>
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php 
</p>
<p>
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php 
</p>
<br />

<p>
  <img width="1166" alt="18" src="https://github.com/user-attachments/assets/33178d46-4b13-4470-b653-e4227ae20078" />
</p>
<p>
  Then we will assign permissions of that file so osTicket can use it with these steps: Right Click file > Properties > Security > Advanced > Disable Inheritance > Remove all inherited permissions from this object.
  

</p>
<br />

<p>
  <img width="1159" alt="19" src="https://github.com/user-attachments/assets/06d1643b-b28a-4e8a-800d-a678ec27b9d6" />
</p>
<p>
  You can see that the permissions were deleted.
  
</p>
<br />

<p>
  <img width="1222" alt="20" src="https://github.com/user-attachments/assets/b08a3f68-9351-4df5-aa27-5022c751051e" />
  
<img width="1212" alt="21" src="https://github.com/user-attachments/assets/fd0be893-d878-4175-bb96-54c060d690e7" />
</p>
<p>
Now that we have deleted the permissions we will add a new permission with these steps: Add > Select a principal > Type ‘everyone’ > Check box next to Full Control > OK 

</p>
<br />

<p>
<img width="1212" alt="21" src="https://github.com/user-attachments/assets/225f8e13-17f5-45d0-9d69-7bc7fdbc01dc" />
</p>
<p>
  The permission should look like this.

</p>
<br />

<p>
<img width="2560" alt="23" src="https://github.com/user-attachments/assets/1ac58186-14c0-4add-ab2b-cb089204132b" />
</p>
<p>
  Go back to the osTicket site and press continue and fill out the blank spaces until the Admin User tabs. 

</p>
<br />

<p>
<img width="593" alt="24" src="https://github.com/user-attachments/assets/1779e7f7-c786-414a-bc5b-09beef38d053" />
</p>
<p>
  Before continuing to the Database Settings tabs we need to install HeidiSQL. Using the HeidiSQL we will be making a connection to the database and setup a database that osTicket can use.  

</p>
<br />


<p>
<img width="682" alt="25" src="https://github.com/user-attachments/assets/e093c05a-5584-478f-bf4c-22f91d39d623" />
</p>
<p>
  Follow these steps: New > Type “root” for the user and password > Open 

</p>
<br />

<p>
<img width="934" alt="26" src="https://github.com/user-attachments/assets/5d3f9779-1979-4437-b910-ba9e5989f151" />
</p>
<p>
We have connected to the database and your page should look like this.

</p>
<br />

<p>
<img width="932" alt="27" src="https://github.com/user-attachments/assets/d7079d9f-7083-4242-a1cf-2ccc323a9ebc" />
</p>
<p>
Now that we have connected to the database we will create a database for osTicket. Right Click Unnamed > Create New > Database and name it “osTicket” 

</p>
<br />

<p>
<img width="2560" alt="28" src="https://github.com/user-attachments/assets/88738529-a664-440b-a15d-1f47175f6333" />
</p>
<p>
Go back to the osTicket site and fillout the Database Settings tabs. Then press Install Now. 

</p>
<br />

<p>
<img width="2560" alt="29" src="https://github.com/user-attachments/assets/731436d4-435a-4e20-ad72-5a6741704a6a" />
</p>
<p>
When the osTicket was successfully downloads, refresh the osTicket database that we created and you will see the filled database.  

</p>
<br />

<p>
<img width="2560" alt="30" src="https://github.com/user-attachments/assets/93e22443-a30c-409c-a58f-2ca5d2b984e3" />
</p>
<p>
Congratulations! We have downloaded osTicket and it is ready to use. 
</p>


