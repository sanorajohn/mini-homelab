## Group Creation in AD

## What I Did
- Opened Active Directory Users and Computers
- Created OUs for each department (HR, IT, Sales)
- Created a security group inside each OU
- Named them based on the department (HR_Users, IT_Users, Sales_Users)
- Added the correct users to each group using the members tab

## Skills Practiced
-Creating security groups
-Understanding group scope and purpose
-Adding users to groups
-Organizing AD objects inside OUs

## Tools Used
-Active Directory Users and Computers

## What I Learned
- Groups are used to manage permissions and policies
- Users should be added to groups instead of assigning permissions individually
- Keeping groups inside the correct OU helps with organization and GPO targeting

Screenshot of Groups Created
(No screenshot available — groups were created before documentation)




## Group Policy Practice – Applying a GPO


## What I Did
- Opened Group Policy Management
- Created a new GPO and linked it to the HR OU
- Edited the GPO to configure a simple setting (password policy)
-Verified the policy applied successfully

## Skills Practiced
- Navigating Group Policy Management
- Creating and linking GPOs
- Editing User and Computer configuration settings
- Testing GPO application on a domain‑joined machine

## Tools Used
- Group Policy Management
- Windows 10 Client VM


## What I Learned
- GPOs allow centralized control over user and computer settings
- Linking a GPO to an OU targets only the users/computers inside that OU
- Policies require correct DNS and domain connectivity to apply



## Screenshots  
All screenshots for this lab are available here:  
[Step 4 Screenshots](./step4-screenshoots.md)




