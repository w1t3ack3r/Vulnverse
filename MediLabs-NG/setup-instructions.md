# MediLabs NG: Setup Instructions ⚙️

Welcome to MediLabs NG, a beginner-to-intermediate vulnerable machine designed for hands-on penetration testing practice. This guide will help you set up the machine.

## Prerequisites

* **Virtualization Software:** Oracle VirtualBox (Recommended) or VMware Workstation/Player.
* **Internet Connection:** To download the virtual machine image.
* Sufficient disk space (approx. 5-10GB) and RAM (min. 512MB, 1GB recommended) for the VM.

## 1. Download the Virtual Machine (.ova file)

The `MediLabs-NG.ova` virtual machine image is hosted on Google Drive.

* **Download Link:** **[🚨 YOUR GOOGLE DRIVE DOWNLOAD LINK FOR MediLabs-NG.ova GOES HERE 🚨]**
    * *Instructions for users: Click the link above to download the `MediLabs-NG.ova` file. You might need to click a "Download anyway" button if Google Drive warns about not being able to scan large files for viruses.*

Please ensure you have downloaded the `.ova` file before proceeding to the next step.

## 2. Importing the Virtual Machine

1.  **Open VirtualBox:** Launch your Oracle VirtualBox software.
2.  **Import Appliance:**
    * Go to `File` -> `Import Appliance...`.
    * Click the folder icon next to the `File` field and browse to the location where you saved the downloaded `MediLabs-NG.ova` file. Select it and click `Open`.
    * Click `Next`.
3.  **Appliance Settings:**
    * You can review the default settings. It's generally fine to leave them as they are. You can adjust RAM or CPU allocation later if needed, but the defaults should work.
    * Ensure the "MAC Address Policy" is set to "Generate new MAC addresses for all network adapters" to avoid conflicts if you import multiple instances.
    * Click `Import`.
4.  **Wait for Import:** The import process may take a few minutes.

## 3. Network Configuration 🌐

For the intended experience (simulating an internal server), the VM should be on a network where your attacker machine can reach it.or VMware Workstation/Player

* **Host-Only Adapter (Recommended for Beginners):**
    1.  Once imported, select `MediLabs NG` in VirtualBox and click `Settings`.
    2.  Go to the `Network` section.
    3.  For `Adapter 1`, ensure it's `Enabled` and set `Attached to:` to `Host-only Adapter`.
    4.  Select a host-only network name (e.g., `vboxnet0`). If you don't have one, you can create it via `File` -> `Host Network Manager...` in VirtualBox (ensure DHCP Server is enabled for the host-only network, usually default).
    5.  **Your attacker machine (e.g., Kali Linux VM or your host OS) must also have an interface on this same host-only network.** This usually means adding a second network adapter to your attacker VM and setting it to the same host-only network.
    6.  The MediLabs NG VM is configured to get an IP address via DHCP on this interface.

* **NAT Network (Alternative):**
    * If you prefer, you can use a `NAT Network`. This also allows communication between VMs on the same NAT network and can provide internet access to the VM if needed (though not required for this challenge).
    * Create a NAT Network in VirtualBox (`File` -> `Host Tools` -> `Network Manager` -> `NAT Networks` tab -> `Create`).
    * Assign `Adapter 1` of MediLabs NG to this NAT Network. Your attacker VM should also be on this same NAT network.

* **Bridged Adapter (Use with Caution):**
    * This connects the VM directly to your physical network, like another physical machine.
    * Only use this if you understand the implications and your network environment. The VM will get an IP from your LAN's DHCP server.

## 4. Starting and Accessing the Machine

1.  **Start the VM:** Select `MediLabs NG` in VirtualBox and click `Start`.
2.  **Identify IP Address:**
    * The VM will boot to a login prompt. You do not need to log in to the console to discover its IP address.

## 5. Initial Configuration (None Required)

The machine is designed to be exploitable out-of-the-box once you have network connectivity. No further configuration within the VM is needed to start the penetration test.

Happy Hacking! 💻

---
