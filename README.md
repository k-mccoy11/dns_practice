<p align="center">
<img src="https://github.com/user-attachments/assets/e7adbe0d-3da8-462b-8fb3-440cc16e78c8"/>

</p>

<h1 align="center">DNS Records Lab in Azure</h1>
<p>This tutorial covers A-records, DNS caching, and CNAME records, reinforcing key DNS management concepts in an Azure-based lab environment. <br />
</p>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- DNS Server Role
-Command Prompt / PowerShell
- Windows Client 
- Windows Server

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
-(Windows Server 2022 

<h2>High-Level Steps</h2>

- Power On VMs:
- A-Record
- Local DNS Cache
- CNAME Record

<h2>Actions and Observations</h2>

<h4></h4>
<p>Ensure Domain Controller-1 and Device-1 are running in the Azure Portal.
</p>
<p>
<ul>
<li>Log into DC-1 and Device-1 using admin credentials.</li>
<li>Attempt to ping “mainframe” from Device-1 (it will fail).</li>
  <p>
<img src=""/>
</p>
<li>Create a DNS A-record for "mainframe" on DC-1, pointing to DC-1’s private IP.</li>
  <p>
<img src=""/>
</p>
<li>Retry pinging “mainframe” from Device-1 (it should now succeed).</li>
  <p>
<img src=""/>
</p>
</ul>
</p>
<br/>

<h4>Local DNS Cache </h4>
<p></p>
<p>
<ul>
<li>Modify mainframe’s DNS record on DC-1 to 8.8.8.8.</li>
  <p>
<img src=""/>
</p>
<li>Ping "mainframe" from Client-1 and observe that it still resolves the old address.</li>
  <p>
<img src=""/>
</p>
<li>Display the local DNS cache (ipconfig /displaydns).</li>
  <p>
<img src=""/>
</p>
  <li>Flush the DNS cache (ipconfig /flushdns) and verify that it clears.</li>
  <p>
<img src=""/>
</p>
  <li>Ping "mainframe" again to confirm it resolves to the updated address.</li>
  <p>
<img src=""/>
</p>
</ul>
</p>
<br/>

<h4>CNAME Record </h4>
<p></p>
<p>
<ul>
<li>Create a CNAME record on DC-1, pointing "search" to "www.google.com".</li>
  <p>
<img src=""/>
</p>
<li>Ping "search" from Client-1 and observe the results.</li>
  <p>
<img src=""/>
</p>
<li>Use nslookup “search” to verify the CNAME resolution.</li>
  <p>
<img src=""/>
</p>
</ul>
</p>
<br/>

Complete: Stop VMs in Azure 
