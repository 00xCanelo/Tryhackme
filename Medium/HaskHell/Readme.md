# 🐾 [HaskHell Lab Writeup](https://tryhackme.com/r/room/haskhell)   
**This is a free TryHackMe lab classified as a Medium Lab.**

---

## 📝 **Lab Overview**  
> _In my assessment, this lab is classified as medium difficulty. While I initially found it to be straightforward, the most challenging aspect was gaining initial access._

---

### 🕵️ **Reconnaissance**  
> **Commencing with a preliminary Nmap scan:**

![](./Images/Screenshot%202024-11-03%20034907.png)  
![](./Images/Screenshot%202024-11-03%20035049.png)  

---

### 🌐 **Website Reconnaissance**  
Next, we will explore the website to identify potential directories.

![](./Images/Screenshot%202024-11-03%20035243.png)  
![](./Images/Screenshot%202024-11-03%20035310.png)  
![](./Images/Screenshot%202024-11-03%20035412.png)  

---

### 🐞 **Exploring Vulnerabilities for Access**  
We can attempt to gain access using the upload page.

![](./Images/Screenshot%202024-11-03%20035430.png)  
![](./Images/Screenshot%202024-11-03%20035829.png)  
![](./Images/Screenshot%202024-11-03%20035856.png)  

### The `.hs` file we uploaded is being rendered, allowing us to execute a simple script for access.

---

### 🚀 **Achieving Initial Access**  

![](./Images/Screenshot%202024-11-03%20040215.png)  
![](./Images/Screenshot%202024-11-03%20040250.png)  
![](./Images/Screenshot%202024-11-03%20040336.png)  

---

### **Logging in as Another User** 👤

![](./Images/Screenshot%202024-11-03%20040557.png)  
![](./Images/Screenshot%202024-11-03%20040803.png)  
![](./Images/Screenshot%202024-11-03%20040854.png)  
![](./Images/Screenshot%202024-11-03%20041030.png)  


--- 

### 👑 **Capturing the Root Flag**  

![](./Images/Screenshot%202024-11-03%20041102.png)  
![](./Images/Screenshot%202024-11-03%20041146.png)  
![](./Images/Screenshot%202024-11-03%20041414.png)  

---

# 💡 **Thank You for Reading!**  
### **Writeup by: [00xCanelo](https://tryhackme.com/r/p/00xCanelo)**
