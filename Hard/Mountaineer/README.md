<p>This is Mountaineer lab in tryhackme this lab is Hard </p>

<p>There are other way that is more easier I chose the long road to help you improve in penetration testing</p>

<p>First we start with nmap scan to all ports</p>

<img src="./Images/Screenshot%202024-10-28%20140042.png"></img>
<img src="./Images/Screenshot%202024-10-28%20140212.png"></img>
<img src="./Images/Screenshot%202024-10-28%20140428.png"></img>
<img src="./Images/Screenshot%202024-10-28%20140626.png"></img>

<p>We need to create the Mountaineer.thm in the /etc/hosts in the kali linux to edit it you need to have the root permission </p>

<img src="./Images/Screenshot%202024-10-28%20140846.png"></img>
<img src="./Images/Screenshot%202024-10-28%20140955.png"></img>

<p>This is a wordpress site so we can start scanning for vulns using wpscan </p> 

<img src="./Images/Screenshot%202024-10-28%20141051.png"></img>
<img src="./Images/Screenshot%202024-10-28%20141138.png"></img>
<img src="./Images/Screenshot%202024-10-28%20141349.png"></img>

<p>Save the usernames to a file like notes because we are going to use it again </p>

<img src="./Images/Screenshot%202024-10-28%20141509.png"></img>

<p>I did simple directory search in the wordpress directory</p>

<img src="./Images/Screenshot%202024-10-28%20142428.png"></img>
<img src="./Images/Screenshot%202024-10-28%20142519.png"></img>
<img src="./Images/Screenshot%202024-10-28%20142637.png"></img>

<p>Add the adminroundcubemail.thm to the /etc/hosts like this:</p> 

<img src="./Images/Screenshot%202024-10-28%20142737.png"></img>
<img src="./Images/Screenshot%202024-10-28%20143914.png"></img>

<p>I used some basic login formats but k2:k2 worked for me I didn’t need to do a bruteforce attack </p>

<img src="./Images/Screenshot%202024-10-28%20144021.png"></img>

<p>Here found a password to login to the page /wp-admin using username : k2 and this password</p>

<img src="./Images/Screenshot%202024-10-28%20144156.png"></img>

<p>We found some info that we can use to create a wordlist we can use later </p>

<p>Now will login like a k2 user</p>

<img src="./Images/Screenshot%202024-10-28%20144443.png"></img>

<p>If we take a closer look at the plugins of the wpscan we did up there we will find that</p>

<p>modern-events-calender-lite is outdated it is using version 6.5.6 using small search you have to do you will find the exploit please do alittle bit of search to help you improve</p>

<img src="./Images/Screenshot%202024-10-28%20145206.png"></img>
<img src="./Images/Screenshot%202024-10-28%20145256.png"></img> 

<p>We are going to create a ReverseShell on port 443 you can use online tools like reverse shell generator and search for nc mkfifo </p>

<img src="./Images/Screenshot%202024-10-28%20145521.png"></img>
<img src="./Images/Screenshot%202024-10-28%20145648.png"></img>

<p>Now we are connected to the machine</p>

<img src="./Images/Screenshot%202024-10-28%20145807.png"></img>

<p>We found an interesting file the Backup.kdbx</p>

<img src="./Images/Screenshot%202024-10-28%20145854.png"></img>
<img src="./Images/Screenshot%202024-10-28%20150008.png"></img>

<p>We need to create a Reverse Shell and output in Backup.kdbx and make a connection from the machine to send the Backup.kdbx</p>

<img src="./Images/Screenshot%202024-10-28%20151122.png"></img>
<img src="./Images/Screenshot%202024-10-28%20151135.png"></img>

<p>Now we need to create some password lists using cupp because we have a lot of info we found in the sent in the mailbox </p>

<img src="./Images/Screenshot%202024-10-28%20151512.png"></img>
<img src="./Images/Screenshot%202024-10-28%20151525.png"></img>

<p>Now we can start crack the backup.kdbx file</p> 

<img src="./Images/Screenshot%202024-10-28%20151702.png"></img>

<p>We found the password</p> 
<p>We can open a the kdbx file using kpcli you can install it from the apt in the linux</p>

<img src="./Images/Screenshot%202024-10-28%20151851.png"></img>
 
<p>Now we need found ssh credentials now we can ssh the to the machine</p>

 <img src="./Images/Screenshot%202024-10-28%20151954.png"></img>
 <img src="./Images/Screenshot%202024-10-28%20152028.png"></img>
 <img src="./Images/Screenshot%202024-10-28%20152135.png"></img>
 
<p>After reading the notes I knew that I can’t do a bruteforce because the password gona be very complex I started looking for more files and I found the .bash_history and I found this </p>

<img src="./Images/Screenshot%202024-10-28%20152212.png"></img>

<p>Nice we found the root password and we can easily find the root flag</p>

<img src="./Images/Screenshot%202024-10-28%20152324.png"></img>

<h2>Useful links:</h2>
<h3>If you didn’t find the exploit for the wordpress this is the link: </h3>
<h4><a href="https://www.exploit-db.com/exploits/50082">Wordpress Exploit</a></h4>

<h1>Thank you for viewing my writeup made by: <a href="https://tryhackme.com/r/p/00xCanelo">00xCanelo</a></h1>
