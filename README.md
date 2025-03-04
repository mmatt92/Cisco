<h1>Cisco Packet Tracer Switch Configuration w/VLAN</h1>



<h2>Description</h2>
In this lab I show the process of configuring a basic switch using commands in Cisco Packet Tracer to connect and seperate a small network using VLAN (Virtual Local Area Network).

 

<br />


<h2>Utilities Used</h2>

- <b>Google</b> 
- <b>Cisco Packet Tracer</b>

<h2>Environments Used </h2>

- <b>Windows 11</b> 

<h2>VLAN Network</h2>

<p align="center">
Open Packet Tracer: <br/>
<img src="https://imgur.com/QryW3Sk.png" height="80%" width="80%" alt="Open packet Tracer"/>
<br />
<br />
Choose (Network Devices) and then click and drag a 2960 switch into work area:  <br/>
<img src="https://imgur.com/EtlKK1N.png" height="80%" width="80%" alt="Select the swtches icon"/>
<br />
<br />
Next select the (End Devices) Icon and click and drag two PCs into work area : <br/>
<img src="https://imgur.com/BAolBoj.png" height="80%" width="80%" alt="Next select the End Devices Icon"/>
<br />
<br />
Now to connect the components select the (Connections) icon and the (Copper Straight-Through). On PC0 connect to FastEthernet0:  <br/>
<img src="https://imgur.com/6mfySWA.png" height="80%" width="80%" alt="Follow Prompts on Screen"/>
<br />
<br />
Connect PC0 to the 2960 switch on FastEthernet0/1:  <br/>
<img src="https://imgur.com/KdKbzdI.png" height="80%" width="80%" alt="Connect PC0 to the 2960 switch on FastEthernet0/1"/>
<br />
<br />
Select (Connections), (Copper Straight-Through), and connect to FastEthernet0 on PC1:  <br/>
<img src="https://imgur.com/iLoqIzl.png" height="80%" width="80%" alt="Congratulations! Your Installation is Complete"/>
<br />
<br />
Connect to the 2960 switch on FastEthernet0/2:  <br/>
<img src="https://imgur.com/wqxARDd.png" height="80%" width="80%" alt="Connect to the 2960 switch on FastEthernet0/2"/>
<br />
<br />
Now to assign IP addresses. Select PC0, Config, FastEthernet0, and enter "192.168.10.1" into the IPV4:  <br/>
<img src="https://imgur.com/IyRLjDe.png" height="80%" width="80%" alt="Now to assign IP addresses"/>
<br />
<br />
Next assign the address for PC1. Select PC1, Config, FastEthernet0, and enter "192.168.10.2" into the IPV4 :  <br/>
<img src="https://imgur.com/f5Ki2pQ.png" height="80%" width="80%" alt="Next assign the address for PC1"/>
<br />
<br />
Test connectivity between PC0 and PC1. Enter PC0, Desktop, Command Prompt, and type "ping 192.168.10.2" enter. The PCs show connectivity because they currently connected on the same VLAN1:  <br/>
<img src="https://imgur.com/0NCyUn2.png" height="80%" width="80%" alt="Test connectivity between PC0 and PC1"/>
<br />
<br />
Now select the 2960 switch and notice on how the description shows the physical ports on the back of the switch. PC0 is connected to Port 1 and PC1 is connected to Port 2:  <br/>
<img src="https://imgur.com/J8aOYKY.png" height="80%" width="80%" alt="Now select the 2960 "/>
<br />
<br />
Next select the CLI and notice the connection that has been established on FastEthernet0/1 (PC0) and FastEthernet0/2 (PC1):  <br/>
<img src="https://imgur.com/rb9g8Xp.png" height="80%" width="80%" alt="Next select the CLI and notice the connection"/>
<br />
<br />
Now to look at current VLAN configuration. Type, enter, enter, "en", enter, "show vlan", enter. VLAN1 is the default and currently has all available ports (1-24) within that network:  <br/>
<img src="https://imgur.com/OzxVlO9.png" height="80%" width="80%" alt="Now to look at current VLAN configuration"/>
<br />
<br />
Next select the CLI and notice the connection that has been established on FastEthernet0/1 (PC0) and FastEthernet0/2 (PC1):  <br/>
<img src="https://imgur.com/rb9g8Xp.png" height="80%" width="80%" alt="Next select the CLI and notice the connection"/>
<br />
<br />
Rename the switch. Type enter, "configure terminal", enter, "hostname S1", enter:  <br/>
<img src="https://imgur.com/ga79O1b.png" height="80%" width="80%" alt="Rename the switch"/>
<br />
<br />
Now to configure the additional VLANs. Type "configure terminal", enter, "vlan 2", enter, "name sales", enter:  <br/>
<img src="https://imgur.com/rgY3Cmb.png" height="80%" width="80%" alt="Now to configure the additional VLANs"/>
<br />
<br />
Next type "exit", enter, "vlan 3", enter, "name parts", enter:  <br/>
<img src="https://imgur.com/ZBwd1zb.png" height="80%" width="80%" alt="vlan 3"/>
<br />
<br />
Verify VLANs have been created. Type "do show vlan", enter. :  <br/>
<img src="https://imgur.com/Bec9z0x.png" height="80%" width="80%" alt="Verify VLANs have been created"/>
<br />
<br />
Now to begin the process of seperating the two PCs onto different VLANs. Type "en", enter, "configure terminal", enter, "interface f0/1", enter, "switchport mode access", enter:  <br/>
<img src="https://imgur.com/FNzVzAv.png" height="80%" width="80%" alt="Now to begin the process of seperating the two PCs"/>
<br />
<br />
Next type "switchport access vlan 2", enter:  <br/>
<img src="https://imgur.com/3j5fDuQ.png" height="80%" width="80%" alt="switchport access vlan 2"/>
<br />
<br />
To verify the port was reassigned type "exit", enter, "exit", enter, "show vlan", enter. Notice now that port f0/1 has been moved to VLAN 2 Sales:  <br/>
<img src="https://imgur.com/gFWGws2.png" height="80%" width="80%" alt="verify the port was reassigned type"/>
<br />
<br />
Next move port g0/2 (f0/2 in switch) to VLAN 3. Type enter, "en", enter, "configure terminal", enter, "interface f0/2", enter, "switchport mode access", enter, "switchport access vlan 3", enter :  <br/>
<img src="https://imgur.com/HgqZqv4.png" height="80%" width="80%" alt="Next move port g0/2 (f0/2 in switch) to VLAN 3"/>
<br />
<br />
Verify again. Type "do show vlan", enter. We can see that port f0/2 has been moved to VLAN 3 Parts:  <br/>
<img src="https://imgur.com/8xmjQYB.png" height="80%" width="80%" alt="Verify again"/>
<br />
<br />
Back in PC0 Command Prompt. If we try to "ping 192.168.10.2" PC1 now, it cannot be reached because the PCs are seperated into different VLANs :  <br/>
<img src="https://imgur.com/RSZqGx7.png" height="80%" width="80%" alt="Verify again"/>
<br />
<br />
End of lab:
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
