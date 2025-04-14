---
Version: 1.0.0  
Date: April 2025  
Author: mdMedia  
Status: Snapshot-ready base lab created
---

# Windows 10 Enterprise Lab Setup on VirtualBox

This is my personal journey setting up a licensed Windows 10 Enterprise (Education Edition) virtual machine using VirtualBox. The goal was to create a stable, snapshot-ready lab environment I could use to practice system administration, security hardening, MMC tools, and real-world IT simulations. I ran into a few setbacks, but I resolved each one — and documented everything here.

---

## Project Goal

I wanted to build a reusable, isolated Windows testbed where I could:

- Use MMC (Microsoft Management Console) tools
- Create and apply Group Policies
- Simulate audit policy changes and log reviews
- Harden the OS as a security exercise
- Run networking and firewall simulations

---

## ⚙️ Tools & Resources

| Tool                                             | Purpose                                      |
| ------------------------------------------------ | -------------------------------------------- |
| [Oracle VirtualBox](https://www.virtualbox.org/) | Virtualization platform                      |
| Windows 10 Education ISO                         | OS installation image (from Azure Dev Tools) |
| Microsoft Azure Dev Tools for Teaching           | Source of the ISO and student product key    |
| Guest Additions ISO                              | Enhances VM performance & features           |

---

## Setup Log

### 1. Downloading the ISO and Key

I signed into [Azure Dev Tools for Teaching](https://aka.ms/devtoolsforteaching) with my student email and downloaded **Windows 10 Education, version 22H2 (64-bit)**. The portal provided me with a unique product key for activation. I saved the ISO locally and backed up the key in my password manager.

### 2. Creating the VM in VirtualBox

I launched VirtualBox and created a new VM manually:

- Name: `Windows10-Edu-Lab`
- Type: Microsoft Windows
- Version: 64-bit
- Memory: 4096 MB
- Disk: 50 GB, dynamically allocated (VDI)

I initially tried VirtualBox’s **Unattended Install**, but ran into an error:  
> *"Windows cannot read the \<ProductKey\> setting from the unattend answer file"*

After some troubleshooting, I restarted the setup and **checked "Skip Unattended Installation"**. That solved the problem and let me proceed manually.

### 3. Mounting the ISO

With the VM created, I went into **Settings > Storage**, clicked the empty optical drive under the IDE controller, and used the disk icon to mount my Windows 10 Education ISO.

### 4. Installing Windows

I started the VM and booted into the Windows setup screen. From there:
- Entered the product key provided by Azure
- Chose the **Windows 10 Education** edition
- Selected a custom install and let it partition the virtual disk

The OS installed successfully after a few restarts, and I created a local admin user to finish setup.

### 5. Activating Windows

After setup, I went to: Settings > System > Activation

At first, Windows didn’t auto-activate — so I manually entered the product key again. This time, activation succeeded, and I now have a digitally licensed, legitimate Windows 10 lab VM.

---

## Installing Guest Additions

The next step was VirtualBox Guest Additions. I selected: Devices > Insert Guest Additions CD image...

But nothing happened — no AutoPlay. I opened **File Explorer > This PC**, found the mounted CD manually, and double-clicked `VBoxWindowsAdditions.exe`.

The installer ran without issue. After rebooting, I had:

- Auto-resizing display
- Bidirectional clipboard
- Drag and drop support

---

## Creating a Snapshot

Before moving on to security labs, I powered off the VM and took a snapshot in VirtualBox:

- Right-click the VM > Snapshots > Take Snapshot
- Snapshot name: `Win10 Education - Clean Install w/ Guest Additions`
- Description: “Clean, activated, fully set up — ready for labs”

---

## What’s Next: Lab Simulations

This base system gives me a solid foundation to test various real-world Windows tasks and simulate sysadmin or security ops scenarios. Here’s what I’ll do next:

### Windows Hardening Projects
- Use `secpol.msc` to configure password and lockout policies
- Enable logon and object access auditing
- Disable unnecessary services using `services.msc`

### User & Group Management
- Create limited users with restricted permissions via `lusrmgr.msc`
- Enforce software restrictions via `gpedit.msc`

### Networking & Security Testing
- Scan the VM from Kali using Nmap
- Monitor responses in **Event Viewer**
- Create and test custom **Windows Firewall** rules

### Tool Installations
- Install the **Sysinternals Suite** (ProcMon, Autoruns, etc.)
- Add **Wireshark** for traffic capture and protocol analysis

---

## Why This Exists

This documentation isn't just a tutorial — it’s a real log of what I did and how I solved common issues. It reflects a working lab system I now use to sharpen my cybersecurity, networking, and Windows sysadmin skills.

---

## Repo Tags
#virtualbox #windows10 #education #vm #sysadmin #networking #cybersecurity #lab #grouppolicy #mmc #studentlabs


---

## Created: April 2025  
**Author**: mdMedia





