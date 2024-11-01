# 🌹 [WhiteRose Lab Writeup](https://tryhackme.com/r/room/whiterose) 🌹  
**This is a free TryHackMe lab classified as an Easy Lab.**

---

## 📝 **Lab Overview**  
> _In my assessment, this room presents challenges that align more closely with a Medium difficulty level rather than Easy._

---

### 🕵️ **Reconnaissance**  
> **Commencing with a preliminary Nmap scan:**

![](./Images/Screenshot%202024-11-01%20181024.png)  
![](./Images/Screenshot%202024-11-01%20181240.png)  
![](./Images/Screenshot%202024-11-01%20181350.png)  
![](./Images/Screenshot%202024-11-01%20181516.png)

---

### 📋 **Hosts File Configuration**  
We need to add `admin.cyprusbank.thm` to `/etc/hosts` on Kali Linux with root permissions.

![](./Images/Screenshot%202024-11-01%20181609.png)

---

### 🌐 **Website Reconnaissance**  
We will proceed to log in using the credentials provided in the room description.

![](./Images/Screenshot%202024-11-01%20181640.png)  
![](./Images/Screenshot%202024-11-01%20181708.png)  
![](./Images/Screenshot%202024-11-01%20182034.png)

### **The telephone number is not visible, possibly due to insufficient access rights.**
### **Let’s explore the possibility of locating another user with elevated privileges.**

---

### 🔍 **Admin User Discovery**  

![](./Images/Screenshot%202024-11-01%20182126.png)  
![](./Images/Screenshot%202024-11-01%20182324.png)

---

### 🐞 **Exploring Vulnerabilities for Access**  

![](./Images/Screenshot%202024-11-01%20182550.png)  
![](./Images/Screenshot%202024-11-01%20182637.png)  
![](./Images/Screenshot%202024-11-01%20182753.png)  
![](./Images/Screenshot%202024-11-01%20182824.png)  
![](./Images/Screenshot%202024-11-01%20182950.png)  
![](./Images/Screenshot%202024-11-01%20183355.png)  
![](./Images/Screenshot%202024-11-01%20183758.png)  
![](./Images/Screenshot%202024-11-01%20183928.png)  
![](./Images/Screenshot%202024-11-01%20184233.png)

---

### 🚀 **Achieving Initial Access**  
This machine is susceptible to EJS Server-Side Template Injection (SSTI). We can utilize the following method to establish a reverse shell.

![](./Images/Screenshot%202024-11-01%20185227.png)  
![](./Images/Screenshot%202024-11-01%20185415.png)  
![](./Images/Screenshot%202024-11-01%20185610.png)  
![](./Images/Screenshot%202024-11-01%20185644.png)  
![](./Images/Screenshot%202024-11-01%20185856.png)

---

### 👑 **Capturing the Root Flag**  

![](./Images/Screenshot%202024-11-01%20185935.png)  
![](./Images/Screenshot%202024-11-01%20190421.png)

### **We can now access the root flag without root privileges.**
### **To do this, we will change the `/etc/shadow` to `/root/root.txt`.**

![](./Images/Screenshot%202024-11-01%20191019.png)

---

## 📚 **Useful Resources**  
- [EJS, Server-side Template Injection RCE (CVE-2022-29078)](https://eslam.io/posts/ejs-server-side-template-injection-rce/)
- [Sudoedit Bypass (CVE-2023-22809)](https://www.vicarius.io/vsociety/posts/cve-2023-22809-sudoedit-bypass-analysis)

---

# 💡 **Thank You for Reading!**  
### **Writeup by: [00xCanelo](https://tryhackme.com/r/p/00xCanelo)**
