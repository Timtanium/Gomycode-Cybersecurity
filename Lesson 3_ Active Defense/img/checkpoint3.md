# CHECKPOINT 3: ACTIVE DEFENSE

# NAME: OBELEAGU CHINAZA TIMOTHY

# OBJECTIVE: To harden administrator accounts and workstations. 

# STEPS:

I downloded the Windows server vm through a link provided 

First, I logged in to the windows server on the server manager, went to :
tools → Active Directory Users and Computers 
![](img)
![
Right click on the user folder and choose the new group : https://i.imgur.com/hBBrhUc.png
Create a group named GOMYCODEstaff: https://i.imgur.com/qzdFvgZ.png
Now leave the User and Group Management and go to :
tools → Active Directory Administrative Center 

On the left side choose:
gomycode (local) → system → Password settings

https://i.imgur.com/Li9iMpb.png

Now on the white space right click and choose new password settings :

https://i.imgur.com/NyUgLE2.png

We want to configure the following policies:
All IT staff privileged accounts must contain a minimum of 20 characters and be complex.
Passwords must be changed every 30 days. Passwords may not be changed more than once per day and the 24 most recent passwords cannot be repeated.
IT staff-privileged accounts are subject to an account lockout policy, with a maximum of three failed login attempts allowed. Accounts will be locked out for a duration of 20 minutes. Reset failed attempts after 10 minutes.
Follow the following screen-shot:  https://i.imgur.com/6qJJQzN.png
Click on add
Type GOMYCODEstaff in the enter the object names to select :  https://i.imgur.com/XIoTBU0.png
Hit OK
Confirm with okay
We can see that the policy was added to the gomycode (local)
Now let’s try to add a group Policy
Go to tools → group policy management : https://i.imgur.com/zyma8tX.png

Name the GPO : SecureAdminWorkstation : https://i.imgur.com/S74LI6q.png

Edit the GPO : (right click + edit):  https://i.imgur.com/Lr5onct.png

Select  Computer Configuration → Policies → Windows Settings → security settings → Local Policies →Security Options :  https://i.imgur.com/3kpqzme.png
Now you can disable Guest Accounts
Change the Administrator account
Choose to not display the last user name in an interactive log-on