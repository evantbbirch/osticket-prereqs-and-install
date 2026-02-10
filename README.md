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

- Microsoft Azure Subscription
- WindowsVM as Host
- WindowsVM as Client
- osTicket
- MySQL
- PHP

<h2>Installation Steps</h2>

Head to the <a href="https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account/search/?ef_id=_k_Cj0KCQiAy6vMBhDCARIsAK8rOgnfYjqkUdUF9wV1PHrfpzFBsthS-0uaZYmS7r0ukqe_-kZXNWWfeeIaAivoEALw_wcB_k_&OCID=AIDcmm5edswduu_SEM__k_Cj0KCQiAy6vMBhDCARIsAK8rOgnfYjqkUdUF9wV1PHrfpzFBsthS-0uaZYmS7r0ukqe_-kZXNWWfeeIaAivoEALw_wcB_k_&gad_source=1&gad_campaignid=21496728177&gclid=Cj0KCQiAy6vMBhDCARIsAK8rOgnfYjqkUdUF9wV1PHrfpzFBsthS-0uaZYmS7r0ukqe_-kZXNWWfeeIaAivoEALw_wcB">Microsoft Azure</a> site and sign up for a subscription to get started.
<p>
<img width="2398" height="944" alt="image" src="https://github.com/user-attachments/assets/b2d1fcc6-e9a7-40db-a21d-839c8a07d798" />
</p>

Once you reach this screen below, go ahead and head to the search bar and search for <b>"virtual machine"</b> and select the "Virtual machines" options under the "Services" section. This will take you to Virtual Machine (or VM, for short) page.
<p>
<img width="1016" height="494" alt="image" src="https://github.com/user-attachments/assets/80a1019e-3110-4c3d-9373-757a50d1e7f4" />
</p>
<br />
Here, create a new VM using either of these buttons and select the one that plainly says "virtual machine".
<p>
<img width="1919" height="932" alt="image" src="https://github.com/user-attachments/assets/498ac379-4d03-4ffe-a8ec-f183fdc86892" />
</p>
<p>
There are a few sections here that are important, and all of these sections are case-sensative, so be sure to be exact when inputting information:
<ol>
  <li>
    Azure Subscription. This should be the subscription you picked when signing up, however, underneath it is the Resource Group section.
    <ul>
      <li>Create a New Resource Group by clicking "Create new" underneath the dropdown</li>
      <li>Name it "osTicket" and click OK</li>
    </ul>
  </li>
  <li>Virtual machine name: osticket-vm</li>
  <li>Region: Choose the best for your use-case. i.e. if you reside on US West, choose the <b>"(US) West US"</b> option. </li>
    <ul>
      <li>Here I'm choosing <b>"(US) East US 2"</b></li>
    </ul>

  <li>Image: This means which Operating System to have on the VM. Choose <b>"Windows 10 Enterprise, version 22H2 - x64 Gen2".</b></li>
  <li>Size: This means how much hardware power will be allocated for this system. We want higher memory since there's a lot of data that would potentially traffic into the ticket system. The cost shown next to this option is saying if the VM were to be running 24/7 for a month, that's how much it would cost.
    <ul>
      <li>Choose <b>"Standard_DS2v3 - 2vcpus, 8GiB memory"</b></li>
    </ul>
  </li>
  <li> Administrator account. For instruction purposes, this username and password is simplified. Please choose a strong password for your use-case.
    <ul>
      <li>Username: ticket-admin</li>
      <li>Password: strongerThanMinePassword!</li>
      <li>Confirm the password you created</li>
    </ul>
  </li>
  <li>Confirm the liscensing at the bottom of the page</li>
</ol>
Any options that were not mentioned on this page are not needed for our implementation.
</p>
<p>
  <img width="387" height="801" alt="image" src="https://github.com/user-attachments/assets/82642718-f144-4822-94ed-8a1e2ea37aa2" />
</p> <br />
<p>
  Select <b>"Next : Disks >"</b> then <b>"Next : Networking >"</b>.
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

Part 1 of 3 complete!
<h2>Continue to Part 2 <a href="https://github.com/evantbbirch/osticket-postinstall-config">here</a>
