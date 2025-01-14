# 🌌 [Mountaineer Lab Writeup](https://tryhackme.com/r/room/mountaineerlinux) 🌌  
**This is a free TryHackMe lab identified as a Hard Lab**

---

## 🔥 **Lab Overview**  
> _There are other ways that are easier; I chose the long road to help you improve in penetration testing._

---

### 🔍 **Recon**  
> **Starting with an Nmap scan on all ports:**

![](./Images/Screenshot%202024-10-28%20140042.png)
![](./Images/Screenshot%202024-10-28%20140212.png)
![](./Images/Screenshot%202024-10-28%20140428.png)
![](./Images/Screenshot%202024-10-28%20140626.png)

---

### 📂 **Hosts File Update**  
We need to add `Mountaineer.thm` to `/etc/hosts` on Kali Linux with root permissions.

![](./Images/Screenshot%202024-10-28%20140846.png)
![](./Images/Screenshot%202024-10-28%20140955.png)

---

### 🔐 **WordPress Vulnerability Scan**  
Since this is a WordPress site, we can start scanning for vulnerabilities using WPScan.

![](./Images/Screenshot%202024-10-28%20141051.png)
![](./Images/Screenshot%202024-10-28%20141138.png)
![](./Images/Screenshot%202024-10-28%20141349.png)

---

### 🔍 **Directory Search**  
> Conducting a simple directory search in the WordPress directory.

![](./Images/Screenshot%202024-10-28%20141509.png)
![](./Images/Screenshot%202024-10-28%20142428.png)
![](./Images/Screenshot%202024-10-28%20142519.png)
![](./Images/Screenshot%202024-10-28%20142637.png)

---

### 📂 **Hosts Update for Admin Access**  
Add `adminroundcubemail.thm` to `/etc/hosts` like this:

![](./Images/Screenshot%202024-10-28%20142737.png)
![](./Images/Screenshot%202024-10-28%20143914.png)

---

### 🔑 **Login**  
Using `k2:k2` to bypass brute force for login.

![](./Images/Screenshot%202024-10-28%20144156.png)

---

### 🔑 **Admin Credentials Found**  
Found credentials to log in to `/wp-admin` with username `k2`.

![](./Images/Screenshot%202024-10-28%20144021.png)

---

### 🔐 **Logging in as k2 User**  

![](./Images/Screenshot%202024-10-28%20144443.png)

---

### 🛠️ **Exploring WordPress Plugins**  
> The `modern-events-calendar-lite` plugin is outdated at version 6.5.6. A small search will reveal the exploit; please search to help improve your skills.

![](./Images/Screenshot%202024-10-28%20145206.png)
![](./Images/Screenshot%202024-10-28%20145256.png)

---

### 🔄 **Setting Up Reverse Shell**  
Creating a reverse shell on port 443; tools like a reverse shell generator can help.

![](./Images/Screenshot%202024-10-28%20145521.png)
![](./Images/Screenshot%202024-10-28%20145648.png)

---

### 🖥️ **Searching through the Machine**  

![](./Images/Screenshot%202024-10-28%20145807.png)

---

### 🗄️ **Finding Interesting Files**  
Discovered a `Backup.kdbx` file.

![](./Images/Screenshot%202024-10-28%20145854.png)


---

### 🛠️ **Reverse Shell for Backup.kdbx Transfer**  
![](./Images/Screenshot%202024-10-28%20150008.png)
![](./Images/Screenshot%202024-10-28%20151122.png)


---

### 📜 **Generating Password Lists**  
Creating custom password lists with `cupp` using information from emails.

![](./Images/Screenshot%202024-10-28%20151512.png)
![](./Images/Screenshot%202024-10-28%20151525.png)

---

### 🔓 **Cracking the Backup.kdbx File**  

![](./Images/Screenshot%202024-10-28%20151135.png)
![](./Images/Screenshot%202024-10-28%20151702.png)

---

### 🔑 **Password Found for kdbx File**  
Using `kpcli` to open the `.kdbx` file.
![](./Images/Screenshot%202024-10-28%20151851.png)

---

### 🔑 **SSH Access**  
Found SSH credentials to access the machine.

![](./Images/Screenshot%202024-10-28%20151954.png)
![](./Images/Screenshot%202024-10-28%20152028.png)
![](./Images/Screenshot%202024-10-28%20152135.png)

---

### 📂 **Analyzing Bash History**  
Discovered the root password in `.bash_history`.

![](./Images/Screenshot%202024-10-28%20152212.png)

---

### 🏆 **Root Access Achieved**  
Using the root password to retrieve the root flag.

![](./Images/Screenshot%202024-10-28%20152324.png)

---

## 🔗 **Useful Links**  
- [WordPress Exploit for version 6.5.6](https://www.exploit-db.com/exploits/50082)

---

# 🙏 **Thank You for Viewing My Writeup!**  
Writeup by: [00xCanelo](https://tryhackme.com/r/p/00xCanelo)
