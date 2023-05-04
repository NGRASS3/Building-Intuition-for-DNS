<p align="center">
<img src="https://i.imgur.com/CtGfsq8.png" alt="osTicket logo"/>
</p>

<h1>Building Intuition for DNS</h1>
In this lab we will be experimenting with DNS. This lab will help us have a better understanding of DNS.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- DNS

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Active Directory Virtual Machine
- Client Machine joined to your domain

<h2>Lab Steps</h2>
<p>
</p>
<p>
To begin we will login to both our DC-1 and Client-1 VM's as admins. From Client-1 we will ping "mainframe". The ping request will not be completed because this record does not exist anywhere. When we send the ping request a series of events takes place:

  - Client-1 will check its own cache to see if it knows mainframe (no result) 
  - Client-1 will then check its local host file @ c:\windows\system32\drivers\etc\hosts (no result) 
  - Finally Client-1 will check the DNS (no result)
</p>

![image](https://user-images.githubusercontent.com/111653930/236297372-c6d7a8cf-7548-4c1d-846f-f4eaa966ddbf.png)

