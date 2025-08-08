# ☁️ **Azure Virtual Machines Projects Portfolio** 💻

Welcome to the **Azure Virtual Machines (VMs) Projects Portfolio!**

This repository showcases practical, real-world implementations and best practices around deploying, managing, securing, and optimizing **Azure Virtual Machines**. These projects are tailored for cloud enthusiasts, beginners, and professionals who wish to **master Infrastructure-as-a-Service (IaaS)** using Microsoft Azure.

---

## 📌 **Table of Contents** 🗂️

1️⃣ **[Introduction](#-introduction)**

2️⃣ **[Why Azure Virtual Machines?](#-why-azure-virtual-machines)**

3️⃣ **[Core VM Concepts](#-core-vm-concepts)**

4️⃣ **[Project Overview](#-project-overview)**

* [Project 1: Creating a Virtual Machine in Azure Portal](#-project-1-creating-a-virtual-machine-in-azure-portal)

5️⃣ **[Step-by-Step Deployment Guide](#-step-by-step-deployment-guide)**

6️⃣ **[Networking & Access](#-networking--access)**

7️⃣ **[Types of Virtual Machines](#-types-of-virtual-machines)**

8️⃣ **[Backup, Recovery, and Monitoring](#-backup-recovery-and-monitoring)**

9️⃣ **[Billing & Cost Management](#-billing--cost-management)**

🔟 **[VM Availability & Scalability Options](#-vm-availability--scalability-options)**

1️⃣1️⃣ **[Conclusion](#-conclusion)**

---

## 📖 **Introduction**

Azure Virtual Machines offer **scalable, flexible, and reliable compute resources** in the cloud. Whether you're running test workloads, deploying web apps, or hosting enterprise-scale services, Azure VMs give you complete control over your infrastructure while removing the burden of physical server maintenance.

This portfolio is designed to give you hands-on experience with Azure Virtual Machines — from basic deployment to advanced optimization. You’ll learn how to configure, manage, and secure VMs, and gain valuable insight into best practices across multiple real-world scenarios.

---

## 🤔 **Why Azure Virtual Machines?**

Virtual Machines in Azure are a key component of cloud architecture. Here’s why they’re so powerful:

* 🔄 **On-Demand Scalability**: Instantly scale your compute power up or down based on workload demands.
* 💰 **Cost Efficiency**: Pay-as-you-go pricing or reserved instances to match your budget.
* 🧱 **Infrastructure Control**: Full control of OS, storage, and applications.
* 🌍 **Global Reach**: Deploy close to your users with data centers across the globe.
* 🔐 **Built-In Security**: Azure integrates security, identity, and monitoring out of the box.

> 📝 **Use Case Examples**:
>
> * Web and API hosting
> * Game and media servers
> * Machine learning experiments
> * Development & testing environments
> * Remote desktops for distributed teams

---

## 🧠 **Core VM Concepts**

Before jumping into projects, it's important to understand the key building blocks of Azure VMs:

* **VM Image**: The OS template used to create your VM (Windows, Ubuntu, etc.)
* **VM Size**: Specifies vCPUs, memory, disk, and network capabilities.
* **Resource Group**: A logical container that holds your VM and related resources.
* **Virtual Network (VNet)**: An isolated network where your VM lives.
* **NSG (Network Security Group)**: Acts like a firewall controlling network access.
* **Disks**:

  * OS Disk: Holds the operating system.
  * Data Disk: Optional storage volumes.
* **Public IP Address**: Needed for remote access.
* **Azure Bastion**: Secure RDP/SSH access without exposing public IPs.
* **Availability Zones**: Improve uptime and fault tolerance.

---

## 🏗️ **Project Overview**

### 🔹 **Project 1: Deploying a Virtual Machine on Azure — A Beginner’s Hands-On Guide**

📌 **Introduction:**
This project is designed to help beginners get hands-on experience by launching their **first VM on Azure** using the Azure Portal. The project walks through key decisions such as VM size, region, OS, networking, authentication, and cost estimates.

✅ **Key Activities:**

* Create a **Resource Group** and **Virtual Network**.
* Deploy a **Windows/Linux VM** from the Azure Portal.
* Configure **public IP**, **inbound port rules**, and **NSG**.
* Choose **VM size**, **OS disk type**, and **location**.
* Connect using **RDP** (Windows) or **SSH** (Linux).
* Use **Azure Bastion** for secure access.

🛠️ **Technologies Used:**

* **Azure Portal**
* **Azure Compute Engine**
* **Azure Resource Manager (ARM)**
* **Network Security Groups (NSGs)**
* **Azure Bastion** (optional)
* **RDP/SSH Clients**

📖 **Use Case:** Perfect for beginners who want to deploy their first VM and understand the essential configurations involved.

---

## 🧱 **Types of Virtual Machines**

Azure offers several VM families, optimized for different workloads. Knowing which VM type to choose is essential for performance and cost control:

| VM Family             | Ideal For                   | Examples           |
| --------------------- | --------------------------- | ------------------ |
| **General Purpose**   | Balanced workloads          | B-series, D-series |
| **Compute Optimized** | High CPU workloads          | F-series           |
| **Memory Optimized**  | Large memory needs          | E-series, M-series |
| **Storage Optimized** | High disk throughput & IOPS | L-series           |
| **GPU**               | Graphics or AI processing   | NC, ND, NV series  |
| **High Performance**  | Scientific simulations      | H-series           |

---

## 📊 **VM Size Comparison Table**

Understanding the sizing options helps right-size your deployments. Each VM size offers a trade-off between cost, performance, and resources:

| VM Size | vCPUs | RAM (GiB) | Temp Storage | Best For                      |
| ------- | ----- | --------- | ------------ | ----------------------------- |
| B1s     | 1     | 1         | 4 GB         | Small dev/test workloads      |
| D2s\_v3 | 2     | 8         | 16 GB        | General workloads             |
| E4s\_v3 | 4     | 32        | 32 GB        | Memory-intensive applications |
| F4s     | 4     | 8         | 32 GB        | High CPU needs                |
| L8s     | 8     | 64        | 128 GB       | High disk throughput          |

---

## 🌐 **Networking & Access**

When deploying a VM in Azure, networking determines how your VM communicates internally and externally.

### Key Networking Components:

* **Virtual Network (VNet):** Your VM is placed in a VNet to communicate securely with other Azure resources.
* **Subnets:** Segment your network logically. Helps with access control and security.
* **Public IP Address:** Used to access the VM over the internet, often via Remote Desktop Protocol (RDP) for Windows or SSH for Linux.
* **Private IP Address:** Used for internal communication within the VNet.
* **Network Security Groups (NSGs):** Define inbound and outbound rules. For example, you might open port 22 (SSH) or 3389 (RDP).

### Access Control:

* **Role-Based Access Control (RBAC):** Determines who can access the VM and what actions they can perform.
* **Azure Bastion:** Provides secure, browser-based access to your VMs without exposing them via public IP.

📝 **Tip:** Always restrict public access unless absolutely necessary. Use NSG rules to limit IP ranges and ports.

---

## 🔐 **Security Best Practices**

* Use **SSH keys** instead of passwords for Linux VMs.
* Use **Azure Bastion** instead of public IPs.
* Apply **NSG rules** to control traffic.
* Enable **Just-in-Time VM Access**.
* Enable **auto OS updates**.
* Turn on **Azure Defender for Cloud** for threat protection.

---

## 💰 **Cost Optimization Strategies**

* Use **B-series** burstable VMs for dev/test workloads.
* Choose **Spot Instances** for interruptible workloads.
* Resize underutilized VMs using **Azure Advisor**.
* Use **reserved instances** for long-term workloads (1 or 3 years).
* Turn off VMs when not in use.

---

## 🔄 **Backup, Recovery, and Monitoring**

Ensuring your VM is protected and monitored is critical for business continuity and operational visibility.

### Backup:

Azure Backup helps you protect VM data by taking regular snapshots and storing them in recovery vaults. You can define backup policies for:

* Daily/weekly backups
* Retention policies
* Application-consistent backups

### Recovery:

Azure Site Recovery allows you to replicate and failover VMs across regions or availability zones during outages. You can:

* Restore an entire VM
* Restore specific files
* Failback when the primary region is restored

### Monitoring:

Azure Monitor and Log Analytics provide:

* Real-time performance data (CPU, memory, disk I/O)
* Alerts and notifications
* Diagnostics logs for auditing and troubleshooting

Use **Azure Advisor** to get personalized recommendations to optimize your VMs.

---

## 💰 Billing & Cost Management

Azure Virtual Machines are billed on a pay-as-you-go model based on:

* **VM size:** Larger VMs cost more.
* **Operating System:** Linux VMs are generally cheaper than Windows.
* **Region:** Prices vary between data centers.
* **Uptime:** You're billed for how long the VM runs (per second, after the first minute).
* **Storage and networking:** OS disk, data disk, outbound bandwidth, and premium SSDs have separate charges.

### Tips to Reduce Costs:

* Use **spot VMs** for interruptible, low-priority workloads.
* Use **auto-shutdown** to avoid running VMs unnecessarily.
* Right-size your VM using **Azure Advisor**.
* Purchase **reserved instances** for 1 or 3 years to save up to 72%.

---

## 🛠️ Additional Key Features of Azure VMs

Here are some other features worth noting:

### 1. **VM Extensions**

Used to automate configuration or install software. For example, you can use the **Custom Script Extension** to run PowerShell or Bash scripts during deployment.

### 2. **Availability Sets and Zones**

Ensure high availability by distributing your VMs across different hardware or regions.

### 3. **Tags**

Tags are metadata attached to resources to help manage costs, ownership, and automation. For example, you can tag a VM by department or environment (e.g., `Environment: Production`).

### 4. **Auto-Scaling with VM Scale Sets**

You can use Azure VM Scale Sets to automatically scale the number of VM instances based on workload or time schedules.

### 5. **DevTest Labs**

Azure DevTest Labs provides a self-service sandbox environment for developers and testers to quickly provision VMs while controlling cost and access.

---

## 📚 **Documentation & References**

* [Azure Virtual Machines Overview](https://learn.microsoft.com/en-us/azure/virtual-machines/)
* [Create a Windows VM](https://learn.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal)
* [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/)
* [Azure Bastion Documentation](https://learn.microsoft.com/en-us/azure/bastion/)

---

## 📩 **Contact Information**

📧 **Email:** [oladosuadeniyi39@gmail.com](mailto:oladosuadeniyi39@gmail.com)
🌐 **LinkedIn:** [Oladosu Ibrahim](https://www.linkedin.com/in/oladosu-ibrahim)
🐙 **GitHub:** [Sudaisib](https://github.com/Sudaisib)

---

## 🚀 **Thank You!**

Thanks for exploring this Azure Virtual Machines Projects Portfolio — may it accelerate your learning journey in cloud infrastructure!
