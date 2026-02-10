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
- WindowsVM as Host Device
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
<h2>Critical Windows Features</h2>
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

<h2>osTicket Dependencies Installation</h2>
<p>
  Now that that's done, let's go ahead and continue with the osTicket installation. Let's go ahead and install these items from the folder:
  <ol>
    <li>Install <b>"PHPManagerForIIS_V1.5.0"</b></li>
    <li>
      Install <b>"rewrite_amd64_en-US"</b>
      <img width="847" height="474" alt="image" src="https://github.com/user-attachments/assets/839818ab-d84d-4618-8f24-ab17d002df6c" />
    </li>
    <li>
      <p>Next, Create a new folder in the C drive (C:\PHP)
<img width="1693" height="949" alt="image" src="https://github.com/user-attachments/assets/a25331b7-cf47-4251-9f62-5171b0e87a02" /></p>
<p>Extract the file <b>"php-7.3.8-nts-Win32-VC15-x86"</b> from the installation files into the new PHP folder.
<img width="2677" height="1236" alt="image" src="https://github.com/user-attachments/assets/918dbe00-bb94-4dfa-98b3-8a2679700127" /></p>
    </li>
    <li>
      Install <b>"VC_redist.x86"</b><img width="1507" height="770" alt="image" src="https://github.com/user-attachments/assets/d7c9a129-d15d-4c8e-8aca-a3a0ac3c8360" />
    </li>
    <li>
      Install <b>"mysql-5.5.62-win32"</b>. This is for the database that store ticket data and user accounts. Once you reach this screen, Make sure to launch the configuration wizard.
      <img width="767" height="594" alt="image" src="https://github.com/user-attachments/assets/0376c39d-0f18-4711-828f-27674d91602d" />
      <ul>
        <li>Select the <b>Standard Configuration</b> then Next.</li>
        <li>You should see this screen below. Set the Root password to a secure password. For demo purposes, I'm setting it to "root" and then confirm your password.<p><img width="371" height="283" alt="image" src="https://github.com/user-attachments/assets/520a222c-8af1-4452-aa7f-d6a2ee1715a8" /></p></li>
        <li>Next, Execute, and Finish.</li>
      </ul>
    </li>
    <li>Now we need to register PHP from within Internet Information Services (or IIS, one of the Windows Features we enabled). Go to the Start Menu and type in "iis" and you should see this application. Run as Administrator.<p><img width="1248" height="1020" alt="image" src="https://github.com/user-attachments/assets/1ef90f2b-315b-4bdc-8f4d-fba6ce7a5fe6" />
</p></li>
    <ul>
      <li>Find the PHP Manager and double click to get to it's settings.<img width="1673" height="799" alt="image" src="https://github.com/user-attachments/assets/3ea4f327-c1b5-4aa1-a77a-0108243019cd" /></li>
      <li>Click <b>"Register new PHP version"</b> and find the executable that is in the PHP folder we created. The file name of that application should be <b>"php-cgi"</b>.<p><img width="1670" height="587" alt="image" src="https://github.com/user-attachments/assets/c4d3b5dc-e85b-4ae2-84ce-9befc8e2b5df" /></p></li>
      <li>Stop and Start the web server by right clicking the root and selecting the appropiate options. They are also in the Actions column on the right-hand side.<p><img width="1666" height="617" alt="image" src="https://github.com/user-attachments/assets/b9a145e7-0aa9-4c31-b2e1-8047cc7828a8" /></p></li>
    </ul>
  </ol>
</p>
<h2>osTicket Installation</h2>
<p>
  <ol>
    <li>Take the <b>"osTicket-v1.15.8.zip"</b> file and extract the files, it can stay in the installation files folder. 
      <p>In the unzipped folder:</p>
      <ol>
        <li>Copy the <b>"upload"</b> folder and place it in <b>"C:\inetpub\wwwroot"</b></li>
        <li>In <b>"C:\inetpub\wwwroot"</b>, rename <b>"upload"</b> to <b>"osTicket".</b><p><img width="2140" height="766" alt="image" src="https://github.com/user-attachments/assets/a66a09ea-2361-4baa-878b-06bd581037ee" /></p></li>
        <li>Stop and Start the IIS Server again.</li>
      </ol>
    </li>
    <li>While still in IIS go to the osTicket site by following the dropdowns and clicking <b>"Browse *:80(http)</b> on the right-hand side.<p><img width="835" height="403" alt="image" src="https://github.com/user-attachments/assets/1cd658ce-9ef8-427b-8ded-72e7f30bdb6a" /></p>
    <p>You should see this landing page:<img width="1880" height="1542" alt="image" src="https://github.com/user-attachments/assets/4ab56329-f632-4910-96d6-99558ffec0ae" /></p></li>
    <li>
      Some extension you see are not enabled. We will enable a few more. Back in IIS, go to the PHP Manager while on the <b>"osTicket"</b> folder.
      <ul>
        <li>In the PHP Extensions section, click <b>Enable or disable an extention"</b>.<p><img width="836" height="495" alt="image" src="https://github.com/user-attachments/assets/5200ff47-e62a-4d3c-84ea-ef7ae21c0349" /></p></li>
        <li><p>Enable these extensions by selecting, then clicking <b>"Enable"</b> on the right-hand side on IIS. <img width="833" height="608" alt="image" src="https://github.com/user-attachments/assets/77de6abb-a19e-4248-9e56-97053ad64327" /></p>
          <ul>
            <li>php_imap.dll</li>
            <li>php_intl.dll</li>
            <li>php_opcache.dll</li>
          </ul>
        </li>
        <li>When you refresh the brower, it should look like this now:<p><img width="1880" height="1547" alt="image" src="https://github.com/user-attachments/assets/548d9e3f-b935-4beb-ad55-47028b4a748a" /></p></li>
      </ul>
    </li>
    <li> Now, we need to rename the <b>"ost-sampleconfig.php</b> file. We're simply omitting the "sample" for cleanup.</li>
    <ul>
      <li>From: C:\inetpub.wwwroot\osTicket\include\ost-sampleconfig.php</li>
      <li>To: C:\inetpub\wwwroot\osTicket\include\ost-config.php<p><img width="1056" height="768" alt="image" src="https://github.com/user-attachments/assets/ebd70dc2-3fd9-465d-be42-7125c1455ced" /></p></li>
    </ul>
    <li> Assign Permissions to that config file. Please assign your permissions as they are necessary for your environment. For purposes of setup, this will be set to everyone with full access.</li>
    <ol>
      <li>Right click > Properties > Security > Advanced<p><img width="1142" height="794" alt="image" src="https://github.com/user-attachments/assets/d8a6dc8c-356e-4d78-bb6d-551062a776ba" /></p></li>
      <li>Disable Inheritance > Remove All</li>
      <li>Once Emptied, hit Add > Select a principal > Everyone</li>
      <p>It sholuld look something like this:<p><img width="574" height="397" alt="image" src="https://github.com/user-attachments/assets/4ffb96a8-1bb3-4112-ae65-fca4dd761a0c" /></p></p>
    </ol>
    <li>We can finally hit that <b>"Continue >>"</b> button on the installer in the web browser!<p><img width="1875" height="1548" alt="image" src="https://github.com/user-attachments/assets/6b138c0f-a257-45a2-8c88-2c48e5e870c1" /></p></li>
    <li>Input all the necessary criteria for your environment for the System Settings and Admin User sections.<p><img width="1876" height="2023" alt="image" src="https://github.com/user-attachments/assets/f5845959-5950-4293-a656-dffdb5436434" /></p></li>
    <li>We need to connect to the database. So we have 1 more setup executable in our installation folder. Run <b>"HeidiSQL_12.3.0.6589_Setup"</b>. Leave everything default.<p><img width="528" height="385" alt="image" src="https://github.com/user-attachments/assets/5d5ec839-da5f-488f-94ec-0101e3f4e04d" /></p></li>
    <li>Once the application is running, hit <b>"New"</b>. Input the password you made for the SQL server, and hit <b>"Open</b><p><img width="1026" height="719" alt="image" src="https://github.com/user-attachments/assets/b73dd794-5217-4a26-bfca-a4bea2f62d7e" /></p></li>
    <li>Create a database, as shown named <b>"osTicket"</b>.<p><img width="1401" height="891" alt="image" src="https://github.com/user-attachments/assets/fd73d252-b598-4a5d-bcae-2491cef3bfc5" />
</p></li>
    <li>Our brower application is now connected to our SQL server! Input the name of the database as you input it, as well as the database username and password and click <b>"Install Now"</b>.</li>
    <li>Voila!<p><img width="1877" height="1266" alt="image" src="https://github.com/user-attachments/assets/d41f221e-cb51-446a-ae64-4da0554eddf5" /></p></li>
    <li>
      One last small step is cleaning up to reduce clutter on the VM.
      <ul>
        <li>Delete <b>"C:\inetpub\wwwroot\osTicket\setup"</b></li>
        <li>Set Permissions to "Read Only": <b>"C:\inetpub\wwwroot\osTicket\include\ost-config.php"</b>
      </ul>
    </li>
    <li>You can now move on to Post-Install Setup by clicking the Admin Panel link on the right side!</li>
  </ol>
</p>
<!--
Part 1 of 3 complete!
<h2>Continue to Part 2 <a href="https://github.com/evantbbirch/osticket-postinstall-config">here</a>
-->
