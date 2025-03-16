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
- Windows Server 2022 

<h2>High-Level Steps</h2>

- Power On VMs:
- A-Record
- Local DNS Cache
- CNAME Record

<h2>Actions and Observations</h2>

<h4></h4>
<p>Ensure Domain-Controller and Device-1 are running in the Azure Portal.
</p>
<p>
<ul>
<li>Log into Domain-Controller and Device-1 using admin credentials.</li>
<li>Attempt to ping “powerpuff” from Device-1 (it will fail).</li>
  <p>
<img src="https://github.com/user-attachments/assets/fd1a16f3-4423-4bda-b716-ea01394fd132"/>
</p>
  In Domain-Controller:
<li> Create a DNS A-record for "powerpuff" on Domain-Controller, pointing to Domain-Controller’s private IP.</li>

  <br/>

  ![image](https://github.com/user-attachments/assets/a745f72d-534e-431e-a5d6-4979a0c47f14)

<br/>

![image](https://github.com/user-attachments/assets/462ed7c2-7261-4295-af2e-af2b3180020a)

<br/>

![image](https://github.com/user-attachments/assets/517d40c2-d546-43ca-a3d7-f0964e2246d9)

<br/>

![image](https://github.com/user-attachments/assets/f2614b9d-3317-4460-ade1-0bed729e9e3f)

<br/>

![image](https://github.com/user-attachments/assets/2586546f-7ee7-43c0-b118-3b7ec95357db)

<br/>

![image](https://github.com/user-attachments/assets/911d57f9-3399-452c-a0c0-63704946dd2c)

<br/>

<li>Retry pinging “powerpuff” from Device-1 (it should now succeed).</li>

<br/>

![image](https://github.com/user-attachments/assets/c864cfbe-f1a9-4458-a246-117ad6fbddb7)
<br/>
</ul>
</p>
<br/>

<h4>Local DNS Cache </h4>
<p></p>
<p>
<ul>
<li>Modify powerpuff’s DNS record on DC-1 to 8.8.8.8.</li>

  ![image](https://github.com/user-attachments/assets/911d57f9-3399-452c-a0c0-63704946dd2c)
  <br/>
<li> Display the local DNS cache (ipconfig /displaydns).</li>
 
 ![image](https://github.com/user-attachments/assets/78213e7b-6dd0-4e46-a3d2-07dac22c2137)

 <h6> If needed, flush the DNS cache (ipconfig /flushdns).</h6>
<br/>

<h4>CNAME Record </h4>
<p></p>
<p>
<ul>
<li>Create a CNAME record on Domain-Controller, pointing "search" to "www.google.com".</li>
 <br/>
  
  ![image](https://github.com/user-attachments/assets/567e56cf-17a0-4653-9d63-5e8aa1846149)
<br/>
 ![image](https://github.com/user-attachments/assets/04da936f-71b4-40e6-82db-4131bbc23922)
 <br/>
<li>Ping "professor" from Device-1 and observe the results.</li>
  <br/>

  ![image](https://github.com/user-attachments/assets/d4e4d928-4436-49d2-9421-580c20972082)
<br/>
<li>Use nslookup “professor” to verify the CNAME resolution.</li>
<br/> 

![image](https://github.com/user-attachments/assets/27b52c78-4163-47c2-a41e-a92d84431821)

</ul>
</p>
<br/>

Practice Completed: Stop VMs in Azure. Have a great day!
