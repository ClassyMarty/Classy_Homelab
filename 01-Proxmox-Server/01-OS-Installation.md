# Proxmox VE Installation Guide

This document covers the fresh installation of Proxmox Virtual Environment (VE) on bare-metal hardware. It's designed to be generic so anyone can follow along with their own setup.

## Prerequisites
- Intel N100 (or similar mini PC)
- USB drive (4GB+) for installation media
- Network cable connected to LAN

## Step 1: Create Bootable USB
1. Download the latest **Proxmox VE ISO** from [proxmox.com/iso](https://www.proxmox.com/en/downloads)
2. Write it to your USB drive using **BalenaEtcher** or **Rufus**
3. Insert the USB into your N100 and boot into the installer

## Step 2: Initial Install
1. Select **Install Proxmox VE** from the boot menu

>[!NOTE]
> **Boot menu selection**  
> *(Screenshot of Proxmox boot menu with installer highlighted)*

2. Agree to the EULA and select your region/timezone
3. Choose an installation target disk

>[!NOTE]
> **Target disk selection**  
> *(Screenshot of disk selection screen with SDA highlighted)*

> **Warning!** This will overwrite all data on your selected drive.

4. Set your admin password when prompted

## Step 3: Network Configuration
Proxmox will assign a static IP during installation. Make sure to set:
- **Host name:** `pve` (or your preferred server name)
- **IP Address:** `[YOUR-PROXMOX-IP]` (e.g., `192.168.1.10`)
- **Netmask:** `255.255.255.0`
- **Gateway:** `[YOUR-GATEWAY-IP]` (e.g., `192.168.1.1`)
- **DNS Server:** `[YOUR-DNS]` (e.g., `8.8.8.8`)

>[!NOTE]
> **Network configuration screen**  
> *(Screenshot of network setup with all fields filled in)*

## Step 4: Finish & Boot
1. Confirm the installation details and start the installer
2. Once complete, remove the USB key and press Enter to reboot

## After Installation
Visit `https://[YOUR-PROXMOX-IP]:8006` (replace with your actual IP) in your browser to access the web UI.

>[!WARNING]
> Your browser will show a security warning due to Proxmox's self-signed certificate. Click "Advanced > Proceed to..." to log in with the root account and password you set earlier.

## Next Steps
- [Setup GPU Passthrough](../02-GPU-Passthrough.md)
- [Configure USB Drive & Bind Mounts](#)
- [Create First LXC Container](#)
