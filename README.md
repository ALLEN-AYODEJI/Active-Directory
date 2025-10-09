# 🛡️ Active Directory Home Lab with Splunk & Attack Simulation  

## 🎯 Objective  
Build and manage an **Active Directory (AD) environment** in a home lab to gain hands-on experience in both **blue team (defense)** and **red team (offense)** operations. This project simulates a real-world enterprise environment and prepares for SOC analyst workflows.  

---

## 🧩 Skills Learned  
- Active Directory setup and domain management  
- User and machine management in enterprise environments  
- Configuring **Sysmon** for Windows telemetry logging  
- Setting up **Splunk** as a SIEM for log ingestion and analysis  
- Performing red team attacks with **Kali Linux** and **Atomic Red Team**  
- Monitoring and detecting attacks through Splunk dashboards and alerts  
- Creating network diagrams for documentation and interviews  
- Troubleshooting and problem-solving independently  

---

## 🛠️ Tools Used  
- **Windows Server 2022** → Domain Controller setup  
- **Windows 10** → Client workstation  
- **Kali Linux** → Offensive attack simulations  
- **VirtualBox** → Virtualization environment  
- **Sysmon** → Advanced Windows telemetry logging  
- **Splunk** → Security Information and Event Management (SIEM)  
- **Atomic Red Team** → Red team testing framework  

---

## 📷 Documentation    

---
## Network Diagram & Lab Planning

### 🗺️ Network Diagram
This diagram was created to plan the Active Directory home lab and visualise data flows between components.

![Network Diagram](https://github.com/ALLEN-AYODEJI/Active-Directory/blob/e5c6b120eaba11e4901b720442f2016b10c421aa/Active%20Directory.jpg)


### 🔧 How I created the diagram (step-by-step)

1. **Choose a diagram tool**
   - I used **draw.io** (diagrams.net) for quick, clean technical diagrams and easy exporting.

2. **Create a new canvas and set the grid**
   - Created a dark-grid canvas for crisp alignment.
   - Turned on grid/snapping to align icons and connections neatly.

3. **Add core infrastructure icons**
   - Placed icons for:
     - **Splunk Server** (SIEM)
     - **Active Directory / Domain Controller**
     - **Windows 10 client** (target)
     - **Kali Linux** (attacker)
     - **Network switch/router** and **Internet/cloud**
   - Kept icons consistent size for visual balance.

4. **Assign IP addresses and roles**
   - Added labels with static IPs for clarity:
     - Network: `192.168.10.0/24`
     - Splunk Server: `192.168.10.10`
     - Active Directory: `192.168.10.7`
     - Windows 10 (DHCP client): (DHCP)
     - Attacker (Kali): `192.168.10.250`
   - Included short role notes (e.g., “Splunk Universal Forwarder”, “Sysmon”, “Atomic Red Team”).

5. **Map logical connections**
   - Drew connections to show data flow:
     - Solid lines for network connectivity.
     - Dotted/colored lines (green) to show log forwarding paths to Splunk.
   - Ensured attacker node is isolated from forwarding to Splunk (attacker does not send telemetry).

6. **Annotate telemetry & forwarders**
   - Marked which machines will run **Sysmon** and **Splunk Universal Forwarder**.
   - Indicated Splunk ingestion points and which hosts will forward logs.

7. **Export and add to repo**
---

## ⚙️ Virtual Machine Installation & Active Directory Lab Setup

The following VMs were installed and configured using **VirtualBox**:
- **Windows Server 2022** – to serve as the **Active Directory Domain Controller (DC)**.
- **Windows 10** – target client machine, joined to the domain.
- **Kali Linux** – attacker machine for offensive simulation.
- **Ubuntu Server 22.04** – running **Splunk**, the SIEM platform for log ingestion and analysis.

---

### 🖥️ Highlights
- Step-by-step installation of **Windows 10**, **Windows Server 2022**, **Kali Linux**, and **Ubuntu Server 22.04**.  
- Overview of **Active Directory Domain Services (AD DS)**, domain controllers, and **Kerberos authentication**.  
- Verification of ISO downloads using **SHA-256 hashes** to ensure file integrity.  
- Recommendation for **cloud VM providers** (Vultr, Microsoft Azure) for users on **Apple M1/M2/M3** systems due to VirtualBox limitations.  
- Tips on managing **hardware resources** by adjusting **RAM and CPU allocations** per VM.  
- Used **pre-built Kali Linux VirtualBox images** for faster setup.  
- Optimized **Ubuntu Server** resources for Splunk with 8GB RAM and 100GB disk space.

---

### 🧩 Key Insights
- **Building a realistic lab** requires multiple specialized VMs that mirror real-world enterprise environments — each with distinct roles for attack, defense, and monitoring.  
- **VirtualBox** is flexible but hardware-dependent — balancing CPU and RAM ensures smooth multi-VM operation.  
- **Verifying VM images (SHA-256)** reinforces strong security practices from the very beginning.  
- **Cloud alternatives** like Vultr or Azure help bypass hardware or compatibility limitations for Apple Silicon users.  
- **AD DS & Kerberos** form the backbone of secure identity management, ensuring authentication integrity in the lab.  
- **Pre-built Kali images** save setup time and reduce configuration complexity.  
- **Ubuntu resource allocation** reflects awareness of data-heavy operations like log ingestion and Splunk queries.  
- **Manual installations** provide more control, help troubleshoot issues early, and ensure better understanding of each configuration stage.  
- **Practical setup tips** such as sending `Ctrl + Alt + Delete` to VMs, identifying 64-bit vs 32-bit systems, and default Kali credentials improve workflow.  
- **All VMs successfully installed**, forming the foundation for the next step — installing and integrating **Sysmon** and **Splunk Universal Forwarder**.

---

### 📸 Visual References
> Below are screenshots showing the installed VMs and configurations.

| Machine | Description | Screenshot |
|----------|--------------|-------------|
| Windows Server 2022 | Domain Controller setup | ![Windows Server](https://github.com/ALLEN-AYODEJI/Active-Directory/blob/fd71b78f86cf8c96451792e6c69361461be023fa/windows%20server.png) |
| Windows 10 | Target client joined to domain | ![Windows 10](https://github.com/ALLEN-AYODEJI/Active-Directory/blob/d289f199e8bd0531a4e60fe7a1528fd8b5d355ce/Windows1.png) |
| Kali Linux | Attacker machine configuration | ![Kali Linux](https://github.com/ALLEN-AYODEJI/Active-Directory/blob/9d3b986902525ec7e5c574d908d34de6f2f26296/kali.png) |
| Ubuntu Server | Splunk installed and configured | ![Ubuntu Server](./assets/ubuntu-setup.png) |

---




