## Joining Windows 10 to the Domain 

## Date 
5/2026

### What I Did
- Set up a Windows 10 VM in VMware Workstation Pro
- Attempted to join it to the domain (sanoralab.local) 
- Verified network connectivity between the Windows 10 VM and the Domain Controller

### Problem I Ran Into
Windows 10 could not join the domain because it was using a **different DNS server** than the Domain Controller.  
This caused:
- “Domain not found” errors  
- Failure to locate the Domain Controller  
- Windows not recognizing the domain name  

### Root Cause
VMware automatically assigned the Windows 10 VM a DNS server from the NAT network instead of the **Domain Controller’s IP**.  
Since domain joins require the client to use the **DC as its DNS**, the join failed.

### How I Fixed It
- Opened Windows 10 network adapter settings  
- Went into IPv4 properties  
- Manually set the DNS server to the **Domain Controller’s IP address**  
- Saved the settings and restarted the network  
- Verified connectivity using `ping <DC-IP>`  
- Attempted the domain join again  
- Successfully joined the domain after DNS was corrected  

### What I Learned
- Windows clients MUST use the Domain Controller as their DNS server  
- VMware NAT/Host-Only networks can assign incorrect DNS automatically  
- Most domain join issues are DNS-related, not credential-related  
- Always check IP, DNS, and network mode when joining a domain  


# Active Directory Practice – Creating Users

## Date
06/23/2026

## What I Did
- Opened Active Directory Users and Computers 
- Created multiple domain user accounts inside an Organizational Unit 

## Skills Practiced
- Navigating ADUC 
- Creating new user objects
- Setting initial passwords
- Understanding OUs and where users should be stored

## Tools Used
- Server Manager
- Active Directory Users and Computers 

## What I Learned
- How to create domain users in Active Directory
- How OUs help organize users in a domain
- Basics of domain administration

## Screenshot of Users Created
![Active Directory Users](ad_user.png)
