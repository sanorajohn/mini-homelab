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
- Ran `ipconfig` on both the Windows Server 2022 Domain Controller and the Windows 10 VM
- Noticed that the Windows 10 VM was using a different DNS server than the Domain Controller
- Opened VMware network settings and made sure both VMs were on the same network type (NAT/VMnet8)
- Ensured the Windows 10 VM was receiving the correct DNS information from the same network as the Domain Controller
- Verified the DNS and IP settings again using `ipconfig`
- Confirmed connectivity by pinging the Domain Controller
- Attempted the domain join again
- Successfully joined the domain once both machines were using the same DNS source
 

### What I Learned
- Domain joins fail when the client and Domain Controller use different DNS servers
- `ipconfig` is the fastest way to compare network settings between machines
- VMware network modes (NAT, Host-Only, Bridged) can cause mismatched DNS if not aligned
- Both VMs must be on the same virtual network for Active Directory to work properly
- Most domain join issues are DNS or network configuration problems, not credential problems



 

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
