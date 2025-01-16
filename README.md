<h1>AD-Preparing-Active-Directory-In-Azure</h1>

<h2>Description</h2>
This is part 1/3 of building a fully-functioning Active Directory server. Part 1 will focus on making 2 virtual machines and configuring their networks. <br/>
<br />


<h2>Environments and Utilities Used</h2>

- <b>Microsoft Azure</b>
- <b>Virtual Machines</b>
- <b>Remote Desktop Connection</b>


<h2>Operating Systems Used </h2>

- <b>Windows Server </b>
- <b>Windows 10</b>

<h2>Project Walk-through:</h2>

<h3>Make the resource group</h3>
<img src="Screenshot 2025-01-15 214150.png">

<h3>Make a virtual network: MAKE SURE THE VIRTUAL MACHINES AND VIRTUAL NETWORK MADE LATER ARE IN THE SAME REGION.</h3>
<img src="Screenshot 2025-01-15 214317.png">

<h3>Make the first virtual machine: Windows Server. MAKE SURE THEY ARE IN THE SAME VIRTUAL NETWORK AS THE ONE MADE PRIOR</h3>
<img src="Screenshot 2025-01-15 214541.png">
<img src="Screenshot 2025-01-15 214600.png">

<h3>After VM is created, set Domain Controller’s NIC Private IP address to be static</h3>
<img src="Screenshot 2025-01-15 214842.png">
<img src="Screenshot 2025-01-15 214915.png">

<h3>Make the second virtual machine: Windows 10 Pro. MAKE SURE THEY ARE IN THE SAME VIRTUAL NETWORK AS THE ONE MADE PRIOR</h3>
<img src="Screenshot 2025-01-15 215045.png">
<img src="Screenshot 2025-01-15 215104.png">

<h3>After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address. Then from the Azure Portal, restart Client-1.
</h3>
<img src="Screenshot 2025-01-15 215217.png">
<img src="Screenshot 2025-01-15 215235.png">
<img src="Screenshot 2025-01-15 215341.png">
<img src="Screenshot 2025-01-15 215446.png">

<h3>Log into the VM and disable the Windows Firewall (for testing connectivity)</h3>
<img src="Capture2.JPG">

<h3>Login to Client-1. Then attempt to ping DC-1’s private IP address</h3>
 - Ensure the ping succeeded
<img src="Screenshot 2025-01-15 220812.png">
<img src="Annotation 2025-01-16 060959.png">
 - From Client-1, open PowerShell and run ipconfig /all
 - The output for the DNS settings should show DC-1’s private IP Address
<img src="Annotation 2025-01-16 061043.png">


<h2>YOU DID IT. Now, it's time to install Active Directory in the domain controller</h2>
