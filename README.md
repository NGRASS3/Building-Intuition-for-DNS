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

<p>
Next we will login to DC-1 and create an A-Record for "mainframe". Go to Start -> Server Manager -> Tools -> DNS -> DC-1 -> Forward Lookup Zone (hostname to IP) -> mydomain -> right click New Host. We will title this new host as "mainframe" and use DC-1s IP. 
</p>

![image](https://user-images.githubusercontent.com/111653930/236301566-852bebfe-78b2-49bd-9a39-d464c8071263.png)

<p>
Now to test our new A-Record we will log back into Client-1 and ping "mainframe" from the command line and its successful. Now this information will be saved in the Client-1s local cache.
</p>

![image](https://user-images.githubusercontent.com/111653930/236301983-e3609952-f2a1-48a8-925d-3163ccde127d.png)
![image](https://user-images.githubusercontent.com/111653930/236302907-22d5876f-e623-4c82-9afb-8a5c8ff4ef62.png)

<p>
In order to better understand the locacl cache we will now log back into DC-1 and change the "mainframe" records IP to 8.8.8.8. Hit apply changes and log back into Client-1. From Client-1 we will once again ping "mainframe". Even though we changed mainframes IP to 8.8.8.8 and is still pinging 10.0.0.4. The reason for this is because this information still exists in the local DNS cache on Client-1. This is where the command flushdns comes into play. 
  </p>
  
  ![image](https://user-images.githubusercontent.com/111653930/236304946-e719323a-90cc-4f42-9975-75d293ef1614.png)
  ![image](https://user-images.githubusercontent.com/111653930/236305024-ef9f486c-607c-4d4f-a4f4-3ecd014020bb.png)


