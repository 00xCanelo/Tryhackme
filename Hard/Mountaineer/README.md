This is Mountaineer lab in tryhackme this lab is Hard 
There are other way that is more easier I chose the long road to help you improve in penetration testing
First we start with nmap scan to all ports
<img src="./Images/Screenshot%202024-10-28%20140042.png"></img>

We need to create the Mountaineer.thm in the /etc/hosts in the kali linux to edit it you need to have the root permission  
 
This is a wordpress site so we can start scanning for vulns using wpscan 

 
 
Save the usernames to a file like notes because we are going to use it again 
 I did simple directory search in the wordpress directory
   
Add the adminroundcubemail.thm to the /etc/hosts like this: 
   
I used some basic login formats but k2:k2 worked for me I didn’t need to do a bruteforce attack 
Here found a password to login to the page /wp-admin using username : k2 and this password
 
We found some info that we can use to create a wordlist we can use later 
Now will login like a k2 user
 
If we take a closer look at the plugins of the wpscan we did up there we will find that
 modern-events-calender-lite is outdated it is using version 6.5.6 using small search you have to do you will find the exploit please do alittle bit of search to help you improve

 
 
We are going to create a ReverseShell on port 443 you can use online tools like reverse shell generator and search for nc mkfifo 
 
 
Now we are connected to the machine
 
We found an interesting file the Backup.kdbx
 
 
We need to create a Reverse Shell and output in Backup.kdbx and make a connection from the machine to send the Backup.kdbx
 






Now we need to create some password lists using cupp because we have a lot of info we found in the sent in the mailbox 

 
 
Now we can start crack the backup.kdbx file 
 
We found the password 
We can open a the kdbx file using kpcli you can install it from the apt in the linux
 
Now we need found ssh credentials now we can ssh the to the machine
 
 
 
After reading the notes I knew that I can’t do a bruteforce because the password gona be very complex I started looking for more files and I found the .bash_history and I found this 
Nice we found the root password and we can easily find the root flag
 

Useful links:
If you didn’t find the exploit for the wordpress this is the link : 
exploit

Thank you for viewing my writeup made by: 00xCanelo
