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

![Network Diagram](https://github.com/ALLEN-AYODEJI/Active-Directory/blob/e5c6b120eaba11e4901b720442f2016b10c421aa/Active%20Directory.jpg)

### 🗺️ Network Diagram
This diagram was created to plan the Active Directory home lab and visualise data flows between components.
---

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



