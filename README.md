<h1>Packet Tracer - Configuring VLANs</h1>

<p align="center">
This is a network diagarm of a LAN that I'll be segmenting into 3 seperate VLANs: <br/>
<img src="https://i.imgur.com/pWWho7o.png" height="80%" width="80%"/>
<br />
<br />
Through the router's CLI, I'll configure the router's G0/0 interface for VLAN10, G0/1 for VLAN20, and G0/2 for VLAN30. I'll start by configuring the G0/0 interface through Global Configuration mode and assign the gateway IP addresse of the PCs within VLAN10 to this interface. So to do this I'll select the G0/0 interface with the "int g0/0" command and declare the gateway ip address by using the command "ip address 10.0.0.62 255.255.255.192". To enable these changes I'll use the "no shutdown" command. Now I'll repeat these steps for interface G0/1 and G0/2 as applicable: <br/>
<img src="https://i.imgur.com/V2mZ01t.png" height="80%" width="80%"/>
<br />
<br />
To verify the changes I made I'll use the "do show ip int brief" command to view the interface configurations. The 3 gateway ip addresses I configured for each VLAN is shown as expected: <br/>
<img src="https://i.imgur.com/b4Jex7e.png" height="80%" width="80%"/>
<br />
<br />
Now I'll be configuring the switch's interfaces, so I'll enter Global configuration mode on the switch's CLI. I'll select and configure all of the VLAN10 interfaces together using the command "int range g0/1,f3/1,f4/1". I'll configure the interfaces as access ports with the command "switchport mode access". Now i'll assign VLAN10 to the access ports using the "switchport access vlan 10" command. Now I'll repeat these steps for VLAN20 and VLAN30 as applicable: <br/>
<img src="https://i.imgur.com/T8YPPVe.png" height="80%" width="80%"/>
<br />
<br />
I'll verify the configurations I made using the command "do show vlan brief". The brief shows the VLANs I created and all the necessary ports are assigned to the correct VLANS: <br/>
<img src="https://i.imgur.com/brJkHyE.png" height="80%" width="80%"/>
<br />
<br />
I can assign a name to each VLAN using the "name" command. I'll name VLAN10 Engineering, VLAN20 HR, and VLAN30 Sales: <br/>
<img src="https://i.imgur.com/Co2Z5bo.png" height="80%" width="80%"/>
<br />
<br />
Now I'll test the connectivity of the network I configured using PC1 and ping other PCs located in the other VLANs. I was successfully able to ping PC3 (10.0.0.65) located in VLAN20, PC5 (10.0.0.129) located in VLAN30, and even PC2 using VLAN10's broadcast address (10.0.0.63): <br/>
<img src="https://i.imgur.com/sfNmpaL.png" height="80%" width="80%"/>
<br />
<br />
</p>

