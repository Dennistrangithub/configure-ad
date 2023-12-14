<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com/watch?v=Q_lMnhotItc)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

    <h1>Project Overview: Azure VM and Active Directory Setup</h1>
  
  
  <h2>1. Set Up Azure Environment</h2>
    <ul>
        <li>Set up resources in Azure.</li>
        <li>Create a Domain Controller VM (Windows Server 2022) named "DC-1".</li>
        <li>Record the Resource Group and Virtual Network details.</li>
        <li>Configure the Domain Controller's NIC to have a static private IP.</li>
        <li>Create a Client VM (Windows 10) named "Client-1" using the same Resource Group and Virtual Network.</li>
    </ul>

  <h2>2. Establish Connectivity</h2>
    <ul>
        <li>Ensure both VMs are in the same Virtual Network.</li>
        <li>Test connectivity: Log into Client-1, use Remote Desktop, and ping DC-1.</li>
        <li>Enable ICMPv4 on the Domain Controller to allow pinging.</li>
    </ul>

  <h2>3. Install and Configure Active Directory</h2>
    <ul>
        <li>Install Active Directory Domain Services on DC-1.</li>
        <li>Promote DC-1 to a Domain Controller for a new forest (e.g., mydomain.com).</li>
        <li>Restart and log into DC-1 with a new user account.</li>
    </ul>

  <h2>4. Create User Accounts</h2>
    <ul>
        <li>In Active Directory, set up Organizational Units for employees and admins.</li>
        <li>Create a user account (e.g., jane_admin) and add it to the Domain Admins group.</li>
        <li>Use jane_admin for all administrative tasks moving forward.</li>
    </ul>

  <h2>5. Join Client-1 to Domain</h2>
    <ul>
        <li>Update DNS settings for Client-1 to point to DC-1.</li>
        <li>Restart Client-1 and join it to mydomain.com domain.</li>
        <li>Verify the addition of Client-1 in the Domain Controller's Active Directory.</li>
    </ul>

  <h2>6. Configure Remote Desktop Access</h2>
    <ul>
        <li>Log into Client-1 as an administrator and enable Remote Desktop access for domain users.</li>
    </ul>

  <h2>7. Create Additional Users and Test Access</h2>
    <ul>
        <li>Use a PowerShell script to generate and create multiple user accounts.</li>
        <li>Verify new accounts in Active Directory.</li>
        <li>Test login to Client-1 with a new user account.</li>
    </ul>

  <h2>8. Completion</h2>
    <ul>
        <li>Final check and verification of setup and configurations.</li>
    </ul>

</body>
</html>
