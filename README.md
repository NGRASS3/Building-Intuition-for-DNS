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
First we will be inspecting DNS A-Records on the server A records are hostname to IP address mappings. We are going to create an A record on DC-1 for "mainframe" and have it point to DC-1's private IP address. If we try to ping mainframe without setting the DNS record it will not work. When we ping "mainframe" Client-1 is checking the DNS cache, checking its local host file and checking the DNS server. To create an A-record go to the AD->Tools->DNS->DC-1->Forward lookup zones->mydomain.com-> right click and create a new A record, title it mainframe. An A record is hostname to ip address mapping. If we go back to the client machine and ping mainframe we will get a reply. 
</p>
<br />
