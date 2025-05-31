# Installing and Setting Up Proxmox VE

![Proxmox Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/9/92/Logo_Proxmox.svg/2560px-Logo_Proxmox.svg.png)

A step-by-step guide to installing and configuring [Proxmox Virtual Environment (VE)](https://www.proxmox.com/en/proxmox-ve), a powerful open-source virtualization platform for running virtual machines and containers.

---

## ✅ Requirements

- A dedicated machine or server with:
  - 64-bit processor with virtualization support (Intel VT-x or AMD-V)
  - At least 4GB RAM (8GB+ recommended)
  - At least one storage drive
- A stable internet connection
- USB flash drive (8GB or more)
- A client machine for accessing the web UI (e.g., your laptop)

---

## ⬇️ Download Proxmox VE

1. Go to the official [Proxmox Downloads page](https://www.proxmox.com/en/downloads).
2. Download the latest **Proxmox VE ISO Installer**.
3. Verify the ISO checksum (optional but recommended).

---

## 🔥 Create a Bootable USB (Windows Only)

To create a bootable USB for Proxmox VE on Windows:

1. Download and install [**Rufus**](https://rufus.ie/en/).
2. Insert your USB flash drive (8GB or larger).
3. Open Rufus and configure:
   - **Device:** Select your USB drive.
   - **Boot selection:** Choose the downloaded **Proxmox VE ISO**.
   - **Partition scheme:** Select `MBR` or `GPT` (depending on your system).
4. Click **Start** to begin flashing.
5. Once complete, safely eject the USB drive.

> 📷 **Rufus Setup Screenshot**

![Rufus Screenshot](https://i.imgur.com/ZjNwPlU.png)

---

## 💿 Install Proxmox VE

1. Boot your server from the USB.
2. Select `Install Proxmox VE` from the boot menu.
3. Accept the EULA and proceed.
4. Choose target hard disk.
5. Set:
   - Country, Time Zone, Keyboard
   - Admin password and email
   - Hostname and network settings
6. Wait for installation to complete.
7. Reboot the system and remove the USB drive.

> 📷 **Rufus Setup Screenshot**

![Rufus Screenshot](https://i.imgur.com/VMfnjNx.jpeg )
<img src="https://camo.githubusercontent.com/..." data-canonical-src="https://i.imgur.com/VMfnjNx.jpeg" width="400" height="400" />
---

## ⚙️ Post-Installation Setup

1. After reboot, login to the web UI from another device: https://your-server-ip:8006

2. Login with:
   - **User:** `root`
   - **Password:** (the one you set during install)

---

## 🌐 Access the Web Interface

- Make sure you are on the same network as the server.
- Accept the self-signed SSL certificate warning.
- You'll land on the Proxmox dashboard.

---

## 🛠️ Initial Configuration

- Upload ISO images for VMs.
- Configure storage (local, NFS, ZFS, etc.).
- Add network bridges for VMs.
- Create your first VM or LXC container.

---

## 🧰 Optional Tweaks

- Disable subscription nag popup: sed -i.bak "s/data.status !== 'Active'/false/g" /usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js
systemctl restart pveproxy

*(Note: Might need to redo after updates)*

- Setup SSH key login
- Configure email alerts
- Add a backup schedule

---

## ❗ Troubleshooting

- Web UI not loading? Check firewall and network settings.
- Missing ISO uploads? Check `/var/lib/vz/template/iso/`
- Disk space issues? Run `df -h` to inspect partitions.

---

## 📚 Resources

- [Official Proxmox VE Documentation](https://pve.proxmox.com/wiki/Main_Page)
- [Proxmox Forums](https://forum.proxmox.com/)
- [YouTube Tutorials](https://www.youtube.com/results?search_query=proxmox+ve+setup)
- [Reddit r/Proxmox](https://www.reddit.com/r/Proxmox/)

---

## 🧾 License

MIT License – feel free to use and contribute.

---

## ✍️ Author

Malachi Rewane – [@MalachiSec](https://github.com/MalachiSec)
