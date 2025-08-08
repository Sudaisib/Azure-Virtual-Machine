
---

# 🖥️ **Deploying a Virtual Machine on Azure: A Beginner’s Hands-On Guide** 🚀

<img width="1536" height="1024" alt="ChatGPT Image Aug 7, 2025, 08_26_46 PM" src="https://github.com/user-attachments/assets/bb13b8e2-8e5a-4442-8187-38eba5b513e9" />

---

## 🗂️ **Table of Contents**

1️⃣ [📌 Introduction](#-introduction)

2️⃣ [⚙️ Prerequisites](#-prerequisites)

3️⃣ [🧩 Architecture Overview](#-architecture-overview)

4️⃣ [📊 Key Configuration Table](#-key-configuration-table)

5️⃣ [🔧 Step-by-Step Deployment](#-step-by-step-deployment)

6️⃣ [🔐 Assign Access Control Roles](#-assign-access-control-roles)

7️⃣ [⏱️ Configure Idle Timeout](#-configure-idle-timeout)

8️⃣ [💽 Add & Format a Data Disk](#-add--format-a-data-disk)

9️⃣ [🖥️ Remote Access via RDP](#-remote-access-via-rdp)

🔟 [✅ Conclusion](#-conclusion)

1️⃣1️⃣ [📘 Blog Details](#-blog-details)

1️⃣2️⃣ [🤝 Connect & Share](#-connect--share)

---

## 📌 **Introduction**

Virtual Machines (VMs) allow users to simulate a physical computer on the cloud. Whether you're a beginner practicing infrastructure provisioning, a developer testing environments, or an IT admin deploying business applications — **Azure VMs offer scalable, cost-effective compute power**.

This hands-on guide shows you how to deploy a **Windows 10 VM** using the Azure Portal. Along the way, you'll learn how to:

✅ Create a virtual machine and resource group

✅ Secure access via IAM roles

✅ Attach and format a secondary data disk

✅ Access your VM remotely using RDP

✅ Tune idle timeout settings for uninterrupted sessions

No scripting or CLI required — all steps use the Azure Portal UI.

---

## ⚙️ **Prerequisites**

Before you begin:

| Requirement           | Details                                                      |
| --------------------- | ------------------------------------------------------------ |
| 🔐 Azure Subscription | You need an active Microsoft Azure subscription              |
| 🌐 Internet Access    | For remote login and portal configuration                    |
| 💻 Basic Skills       | Familiarity with RDP and cloud service navigation is helpful |

---

## 🧩 **Architecture Overview**

Here’s what we’re building:

* 🖥️ A Windows 10 Virtual Machine hosted in Azure
* 🔒 Role-based access control (RBAC) for secure access
* 💽 An additional data disk for custom file storage
* 🔁 Idle timeout adjustments to keep remote sessions alive
* 🔌 Secure RDP login for remote management

```
             +--------------------------+
             |   Azure Resource Group   |
             +--------------------------+
                        |
                        |
            +----------------------------+
            |   Windows 10 Virtual Machine |
            +----------------------------+
              |            |           |
              |            |           |
         [RDP Access]  [IAM Access]  [Data Disk]
```

---

## 📊 **Key Configuration Table**

| **Setting**         | **Purpose**                           | **Example / Value**                |
| ------------------- | ------------------------------------- | ---------------------------------- |
| VM Image            | Operating system to install           | Windows 10                         |
| VM Size             | Virtual CPU, memory specs             | Standard B2s                       |
| Resource Group Name | Logical container for Azure resources | `IbrahimRG`                        |
| VM Name             | Name of the virtual machine           | `IbrahimVM`                        |
| Admin Credentials   | For logging in remotely               | Username: `sudais` / Your password |
| Inbound Ports       | For network accessibility             | RDP (TCP 3389)                     |
| Tags                | Metadata for billing or tracking      | Department: HR, Purpose: Hire      |
| Additional Disk     | For personal or team storage          | Name: `ibrahim-disk`               |
| Idle Timeout        | Timeout for public IP sessions        | 30 Minutes                         |

---

## 🔧 **Step-by-Step Deployment**

### 1️⃣ **Create a Virtual Machine**

1. Log in to the [Azure Portal](https://portal.azure.com/)
2. In the search bar, type `Virtual Machines` → Click **+ Create**
3. Choose **Resource Group** → *Create new* → Name: `IbrahimRG`
4. Set VM Name: `IbrahimVM`
5. Region: Choose closest to you (e.g., West Europe)
6. Image: Windows 10
7. Size: Choose B2s (for test/dev)
8. Authentication: Username (`sudais`) + Password
9. Allow **RDP (3389)** under inbound ports

### 2️⃣ **Configure Tags**

Tags help you track costs or usage.

| Key        | Value   |
| ---------- | ------- |
| Department | HR      |
| Purpose    | Hire    |
| Staff      | Oladosu |

---

### 3️⃣ **Monitoring & Review**

* Disable Boot diagnostics (optional)
* Click **Review + Create** → Wait for validation
* Click **Create** → Then **Go to Resource**

---

## 🔐 **Assign Access Control Roles**

Use IAM to grant access to team members.

1. Navigate to your VM → Access Control (IAM)
2. Click **+ Add → Add role assignment**
3. Role: `Virtual Machine Administrator Login`
4. Members: Choose a user from your directory
5. Click **Review + assign**

This allows only authorized users to log in and manage the VM.

---

## ⏱️ **Configure Idle Timeout**

To prevent your VM from disconnecting due to inactivity:

1. Go to the VM → Public IP Address
2. Under Settings → **Configuration**
3. Change **Idle timeout (minutes)** to `30`
4. Click **Save**

✅ This ensures longer, uninterrupted remote desktop sessions.

---

## 💽 **Add & Format a Data Disk**

You can attach another disk for additional storage:

1. Go to your VM → **Disks** → Click **+ Create and attach new disk**
2. Name it: `ibrahim-disk`
3. Click **Apply** and **Save**

To format the disk:

1. Connect via RDP
2. Open `Disk Management`
3. Right-click the new unallocated disk → **New Simple Volume**
4. Follow the wizard to assign a letter and format the drive

---

## 🖥️ **Remote Access via RDP**

1. Go to VM Overview
2. Click **Connect → RDP**
3. Download the `.rdp` file and open it
4. Enter your username and password
5. Accept all prompts and connect

🎉 Congratulations! You now have remote access to your VM.

---

## ✅ **Conclusion**

You’ve successfully created a secure, functional Azure VM using the portal. Here's what you achieved:

✅ Deployed a Windows 10 Virtual Machine
✅ Configured access, security, and metadata tags
✅ Extended idle timeout for smooth RDP access
✅ Attached and formatted an additional disk
✅ Practiced key Azure IaaS (Infrastructure as a Service) skills

This project lays the groundwork for future tasks like installing software, deploying web apps, or simulating enterprise-grade virtual infrastructure.

---

## 📘 **Blog Details**

🔗 Read the full article and get full screenshots, tips, and best practices:
👉 [Deploying a Virtual Machine on Azure – Full Guide](https://dev.to/sudaisib/deploying-a-virtual-machine-on-azure-a-beginners-hands-on-guide-5gb)

---

## 🤝 **Connect & Share**

Was this guide helpful?

✅ **Star this repo**
✅ **Share with your community or study group**
✅ Follow me for more hands-on Azure labs:

* [🔗 LinkedIn – Oladosu Ibrahim](https://www.linkedin.com/in/oladosu-ibrahim/)
* [✍️ Dev.to – @sudaisib](https://dev.to/sudaisib)

---

Let me know if you'd like a **downloadable version in PDF**, or a **GitHub repository template** for this guide!

