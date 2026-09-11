## Technical Guide: Installing Ubuntu on Windows Using WSL

Setting up a production-grade Linux environment on a Windows machine without heavy virtual machines or dual-booting is achieved using the Windows Subsystem for Linux (WSL). This guide covers the complete installation and initialization workflow.

### 1. Install WSL

Open **PowerShell** or **Command Prompt** as an administrator (right-click the app icon and select *Run as administrator*), then run the master installation command:

```powershell
wsl --install

```

This automatically enables the required Windows virtualization features and downloads the default Ubuntu distribution.

### 2. Restart Your Computer

Windows requires a system reboot to load the updated WSL kernel and drivers. Close your terminal and restart your PC.

### 3. Initialize Ubuntu

Open your Windows Start menu, search for **Ubuntu**, and launch it. Upon its first boot, the system unpacks its root filesystem and prompts you to configure your credentials:

* Enter your desired UNIX username.
* Type and confirm your password. *(Note: Linux hides your keystrokes for security—no characters or dots will appear as you type).*

### 4. Update Packages & Troubleshoot Network Glitches

Once your terminal prompt updates to your new user and machine handle, synchronize your package manager:

```bash
sudo apt update && sudo apt upgrade -y

```

> **Troubleshooting Tip:** If you encounter `Network is unreachable` errors during the update, Windows and WSL are experiencing a temporary network bridge or DNS conflict. Fix this instantly by opening PowerShell outside of Ubuntu and running:
> ```powershell
> wsl --shutdown
> 
> ```
> 
> 
> Then, reopen your Ubuntu terminal and rerun `sudo apt update`.
