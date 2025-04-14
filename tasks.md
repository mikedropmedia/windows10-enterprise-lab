# Lab TODOs – Windows 10 Enterprise Lab

This file tracks lab simulations and security tasks for my Windows 10 Education VM, set up in VirtualBox. I’ll use this checklist alongside GitHub Issues and snapshots to track progress.

---

## Completed Setup
- [x] Download and install Windows 10 Education ISO
- [x] Manually install with student product key
- [x] Skip Unattended Install in VirtualBox
- [x] Install Guest Additions manually
- [x] Snapshot the base install

---

## Windows Hardening
- [ ] Configure Local Security Policy (`secpol.msc`)
- [ ] Enable audit policy for logon events
- [ ] Disable unnecessary services (`services.msc`)

---

## User & Group Policy
- [ ] Create a limited user account (`lusrmgr.msc`)
- [ ] Apply Group Policy to restrict software or settings (`gpedit.msc`)

---

## Network & Security Simulations
- [ ] Simulate Nmap scan from Kali and analyze logs
- [ ] Monitor login attempts via Event Viewer (`eventvwr.msc`)
- [ ] Create a firewall rule and verify blocked traffic

---

## Tool Installations
- [ ] Download and install Sysinternals Suite
- [ ] Install and test Wireshark inside the VM
