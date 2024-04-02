<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
Project Summary: This Project is a walkthrough of the steps I took to showcase various network protocols in action using Microsoft Azure in the Windows 10 operating System. Using Wireshark to monitor different protocol traffic, we can observe various network traffic to and from Azure Virtual Machines. In this project, we also experiment with Network Security Groups which serve as firewalls between virtual machines.


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Part 1 (Create Resources)
- Part 2 (Observe ICMP Traffic)
- Part 3 (Observe SSH Traffic)
- Part 4 (Observe DHCP Traffic)
- Part 5 (Observe DNS Traffic)
- Part 6 (Observe RDP Traffic)

<h2>Actions and Observations</h2>

<p>
<br>Part 1 (Create Resources) </b>
  <br> - Created a Resource Group </b>
  <br> - While creating VM1, i selected the previously created Resource Group (RG-LAB-02)  </b>
  <br> - While creating VM1, i allowed it to create a new Virtual Network (Vnet) and Subnet in the Networking tab </b>
  <br> - Created a Linux (Ubuntu) VM (VM2) </b>
  <br> - While creating VM2, I selected the previously created Resource Group and Vnet (VM1-vnet) so that both VM's were on the same subnet </b>
  <br> - Observed the Virtual Network within Network Watcher </b>
</p>

![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/0a384cfc-02d4-49b9-a4f9-b9d3c56490a8)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/59e7b50a-bb16-43ae-aa16-25fbfe9216c9)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/95c6a122-4d52-42e8-88c4-cf5459b0e6d4)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/53bea237-6e0d-4853-8036-f534e92e6ee7)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/ce090105-6100-47e4-b81f-98fabca5582a)

<p>
<br> Part 2 (Observe ICMP Traffic) </b>
  <br> - Used Remote Desktop to connect to the Windows 10 Virtual Machine </b>
  <br> - Installed Wireshark in VM1 </b>
  <br> - Opened Wireshark and filtered for ICMP traffic only </b>
  <br> - Retrieved the private IP address of the Ubuntu VM (VM2) and attempted to ping it from within the Windows 10 VM
 </b>
  <br> - Observed ping requests and replies within WireShark </b>
  <br> - From The Windows 10 VM, opene PowerShell and attempted to ping a public website (such as www.google.com) and observed the traffic in WireShark </b>
  <br> - Initiated a perpetual/non-stop ping from the Windows 10 VM (VM1) to THE Ubuntu VM (VM2)
 </b>
 <br> - Opened the Network Security Group the Ubuntu VM (VM2) is using and disabled incoming (inbound) ICMP traffic
 </b>
  <br> - Back in the Windows 10 VM (VM1), observed the ICMP traffic in WireShark and the command line Ping activity
 </b>
 <br> - Re-enabled ICMP traffic for the Network Security Group the Ubuntu VM (VM2) is using
 </b>
  <br> - Back in the Windows 10 VM (VM1), observed the ICMP traffic in WireShark and the command line Ping activity start working again.
 </b>
</p>

![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/b11070be-6790-42ef-9bd2-d1cbc1ada10c)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/a4d6b9bd-f28f-4b56-ba85-7906ad9b4d02)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/e7f89882-07c1-4162-aa7f-09bbf6676a3b)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/5fe1f5a4-c02f-4cd6-b5a1-c839293671f7)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/8adfe425-fbeb-42eb-b305-d90be3111be5)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/de99e1d4-4088-4776-94f1-3e6224ef45ce)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/50c88859-7d5a-4c7d-a0f5-9eedc5802fc9)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/c0c9c703-d8c9-4c67-9175-65d6537132d1)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/a357b375-e2a1-4b12-bd51-18f98585e061)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/1c7b5395-dccb-4a33-a450-ce53694debca)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/2ccc1dd3-e3e3-4b89-bacb-7ca6ecb549a8)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/471317d2-c541-42ce-9b2b-d585f3dfea66)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/2a6d0127-6d1d-4e24-b6bb-95e3d5531a63)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/74bda05c-4564-4977-884b-a3ee2d321376)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/7fa45b28-122b-415e-9c19-48812b22ff89)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/a0db6665-5ae2-4e5b-962d-1c44ce9445eb)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/a6114203-5072-4d82-a6db-128e2696df9f)




<p>
<br> Part 3 (Observe SSH Traffic) </b>
  <br> - Back in Wireshark, I filtered for SSH traffic only </b>
  <br> - From the Windows 10 VM (VM1), I “SSH'ed” into the Ubuntu Virtual Machine (VM2) (via its private IP address) with the user "labuser"
  </b>
  <br> - Typed commands (username, pwd, etc) into the linux SSH connection and observed SSH traffic spam in WireShark
 </b>
 <br> - Exited the SSH connection by typing ‘exit’ and pressing [Enter]
 </b>
</p>

![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/4f46a313-fdd5-47aa-89df-ec2c5580b45f)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/bad78c38-8475-4f56-bc80-c6e0f9bd6fd2)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/3a829fba-83ce-4435-a789-72e62e75df4c)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/249c948c-6993-4720-a918-892c871b81e2)



<p>
<br> Part 4 (Observe DHCP Traffic) </b>
  <br> - Back in Wireshark, I filtered for DHCP traffic only </b>
  <br> - From the Windows 10 VM (VM1), I attempt to issue the VM a new IP address from the command line (ipconfig /renew)  </b>
  <br> - Observed the DHCP traffic appearing in WireShark </b>
</p>

![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/d2c3240f-c91f-4649-8c6f-b939b567e2ed)
![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/4ff573ea-6339-41ea-9932-350d29ca6a0b)



<p>
<br> Part 5 (Observe DNS Traffic) </b>
  <br> - Back in Wireshark, I filtered for DNS traffic only </b>
  <br> - From your Windows 10 VM within a command line, use nslookup to see what google.com's IP addresses are </b>
  <br> - Observe the DNS traffic being show in WireShark </b>
</p>

![image](https://github.com/IZEK4K/azure-network-protocols/assets/90485066/7bcf79e6-7e6e-45b1-bf33-b26b5ad1b713)


<p>
<br> Part 6 (Observe RDP Traffic) </b>
  <br> - Back in Wireshark, filtered for RDP traffic only (tcp.port == 3389) </b>
  <br> - Observed the immediate non-stop spam of traffic due to rdp constantly showing live traffic from one computer to another </b>
</p>












