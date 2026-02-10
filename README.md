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
  Select <b>"Next : Disks >"</b> then <b>"Next : Networking >"</b>. You will see the Virtual Network section autofill along with the subnet and Public IP. These options are okay. You can proceed to <b>"Review + create"</b> and then <b>"Create"</b>. The deployment may take a few minutes.
</p>
<p>
<img width="569" height="841" alt="image" src="https://github.com/user-attachments/assets/f9be0095-abd8-48ee-ae31-4cf4f1a8dccd" />
</p>
<p>
  The VM is created! Now, with the fresh VM, we can install osTicket and it's dependencies. On Azure, head to the VM page and look for the VM's Public IP Address in order to remote connect to the VM.
</p>
<p><img width="1673" height="65" alt="image" src="https://github.com/user-attachments/assets/a666d2f1-7e1d-4956-a583-750de0c41fbb" /></p>
<p>When in the Start Menu on your windows device, type in "remote desktop connection" and select the application. A window will pop up that looks like this.</p>
<p><img width="606" height="370" alt="image" src="https://github.com/user-attachments/assets/45cb4224-9276-4b87-9684-e505ae0c3db1" /></p>
<p>Input the Public IP Address of your VM. When it asks for credentials, do <b>not</b> input yours, but select "Use a different account" and input the credentials for the administrator your created. You may get another popup but just hit yes to proceed to connect.</p>
<h2> Click <a href="https://docs.google.com/document/d/158ESzkK_yZH2rl4_A5fkpZAnSlkvx0g_Fbq7OGWtn5o/edit?usp=sharing">here</a> for the a link to the zip files. </h2>
You can take this link, copy and paste it into the Microsoft Edge browser on the VM, and have it download onto the system that way.
<p><img width="940" height="775" alt="image" src="https://github.com/user-attachments/assets/4ee4c474-ee2b-4dc8-bc6c-27b38ad02a5f" /></p>
<p>
Once it is downloaded, unzip the folder. For ease of the process, onto the desktop is fine.
</p>

<p>
  Before we move further with installation, we need a critical Windows feature enabled.
  <ol>
  <li>Go to Start</li>
  <li>In the Search bar, search <b>"wndows features"</b></li>
  <li>Select <b>"Turn Windows features on or off"</b></li>
  </ol>
  <img width="1248" height="1020" alt="image" src="https://github.com/user-attachments/assets/14c1c92a-4794-4bca-872b-a304555acffc" />
</p>
<p>Enable <b>"Internet Information Services"</b> and <b>"CGI"</b>, as highlighted here.</p>
<p><img width="347" height="443" alt="image" src="https://github.com/user-attachments/assets/9bc46394-26dd-4565-ba67-e009d2fb5df9" /></p>
<br />

Part 1 of 3 complete!
<h2>Continue to Part 2 <a href="https://github.com/evantbbirch/osticket-postinstall-config">here</a>
