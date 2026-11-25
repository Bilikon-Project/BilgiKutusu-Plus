<div align="center">

# 📚 BilgiKutusu Plus
### Knowledge at your side, even without the internet.
**A portable, zero-dependency, offline local network knowledge repository for Raspberry Pi 4.**

<p>
  <img src="https://shields.io" alt="Version 1.0.0" />
  <img src="https://shields.io" alt="Raspberry Pi 4" />
  <img src="https://shields.io" alt="Python 3.9+" />
  <img src="https://shields.io" alt="Offline Usage" />
</p>

<p>
  <a href="README-tr.md">🇹🇷 Türkçe</a> · <b>🇺🇸 English</b>
</p>

<p>
  <a href="#-features">Features</a> •
  <a href="#-whats-in-the-package">Package Contents</a> •
  <a href="#-quick-start">Quick Start</a> •
  <a href="#-installation-on-raspberry-pi">Installation</a> •
  <a href="#-using-content-on-an-ssd">SSD Setup</a> •
  <a href="#%EF%B8%8F-license">License</a>
</p>

<sub>Developer: <a href="https://github.com">@alicanyilmz</a> · Organization: <a href="https://github.com">Bilikon-Project</a></sub>

</div>

---

> [!IMPORTANT]
> **Development Release · 1.0.0**  
> This repository contains the application code, installation scripts, and small sample files for testing purposes. **Book or large media archives are not included in this package.** The included map and video files are for demonstration only. Long-term real hardware and load testing on Raspberry Pi has not yet been verified.

## 🌿 What is BilgiKutusu Plus?

**BilgiKutusu Plus** is a lightweight web portal that lets you access a centralized file archive from phones, tablets, and computers connected to the same local network (Wi-Fi / LAN). Without needing an internet connection, you can browse folders, perform instant file searches, stream browser-compatible videos smoothly, and download documents to your device.

* **Zero External Dependencies:** Uses only the Python standard library; requires no extra packages, databases, or cloud accounts.
* **No AI Involved:** Runs completely deterministically with minimal resource usage.
* **Product Tier:** The mid-tier solution in the BilgiKutusu ecosystem.

| Edition | Target & Scope |
| :--- | :--- |
| **BilgiKutusu Go** | Basic level, lightest starter package |
| **BilgiKutusu Plus** *(This Repo)* | **Mid-tier; enhanced media streaming, filtering, and sample templates** |
| **BilgiKutusu Pro** | Comprehensive, full-featured library interface |

---

## ✨ Features

| Feature | Description |
| :--- | :--- |
| 📂 **File Explorer** | Lists content directories through a clean, mobile-friendly web interface. |
| 🔎 **Instant Search & Filter** | Quickly filters files inside the active folder by filename and media type. |
| 🎬 **Smooth Media Streaming** | Plays browser-supported audio/video files with **HTTP Range** support for seeking. |
| ⬇️ **One-Click Download** | Saves selected files directly to the client device (phone/computer). |
| 💾 **External SSD Support** | The content directory can easily be pointed to an external drive via the configuration file. |
| ⚙️ **Background Service** | Starts automatically at boot on Linux distributions using `systemd`. |
| 🧭 **100% Local Operation** | Makes no external CDN, font, or API requests; works seamlessly in air-gapped networks. |

---

## 📦 What's in the Package?

<details open>
<summary><b>View Default Folders and Sample Content List</b></summary>
<br>

| Section | Included Content | Description |
| :--- | :--- | :--- |
| 🗺️ **Maps** (`Haritalar`) | Turkish city locations image | **Sample map** showing approximate coordinates of 9 city centers (not a detailed map). |
| 🎥 **Educational Videos** (`EgitimVideolari`) | Directions on a map | **24-second text-annotated sample video** explaining compass directions, latitude, and longitude. |
| 🌾 **Agriculture** (`Tarim`) | Planting tracker CSV sheet | Ready-to-use spreadsheet template you can download and edit on your device. |
| 🎣 **Fishing** (`Balikcilik`) | Observation log CSV sheet | Ready-to-use logbook template you can download and edit on your device. |
| 📄 **Documents** (`Belgeler`) | Getting started text | Short guide containing basic usage instructions. |
| 📚 **Books** (`Kitaplar`) | *Empty content area* | Directory reserved for your own e-book/PDF archive. |
| 🖼️ **Images** (`Gorseller`) | *Empty content area* | Directory reserved for your own photos and images. |

</details>

> [!NOTE]
> Wikipedia/ZIM archives, Kiwix, movie/TV series archives, and large educational libraries are **not included** in this package. The application does not automatically download content from the internet; you only add your own files that you have the right to share.

---

## 🧰 Requirements

* **Hardware:** Raspberry Pi 4 Model B *(4 GB RAM recommended)*
* **Operating System:** Raspberry Pi OS or Debian-based Linux distributions
* **Software:** Python `3.9` or higher + `systemd`
* **Storage:** SD card or external SSD sized for your archive *(no fixed 1 TB requirement)*
* **Network:** Shared local network accessible by both the Raspberry Pi and client devices

> [!TIP]
> **Wi-Fi / Access Point Note:** The installation script does not turn your device into a Wi-Fi Hotspot. It uses your existing local network or pre-configured BilgiKutusu network without modifying your existing `nginx`, `Kiwix`, or disk mount settings.

---

## 🚀 Quick Start

To test the application locally without installing it as a system service, download the repository and open a terminal in the project root directory:

```bash
# Start the local test server
bash baslat.sh
```

Open **`http://127.0.0.1:8091`** in your browser. Press `Ctrl + C` in the terminal to stop the server.  
*(Note: For security reasons, quick-start mode is only accessible from the local machine itself by default.)*

---

## 🔧 Installation on Raspberry Pi

To permanently install the application as a system service, run the following command in the project root directory:

```bash
sudo bash kur.sh
```

**Directories created by the installer:**
* **Application files:** `/opt/bilgikutusu-plus`
* **Shared content:** `/srv/bilgikutusu-plus/icerik`
* **Configuration file:** `/etc/bilgikutusu-plus/config.json`

### 📱 Connecting from the Local Network
1. Connect your phone or computer to the **same Wi-Fi / local network** as the Raspberry Pi.
2. Run `hostname -I` in the Raspberry Pi terminal to find its local IP address.
3. Open **`http://PI_IP_ADDRESS:8091`** in your client device's browser.

> [!WARNING]
> The installation script will safely abort if it detects an existing `BilgiKutusu Plus` installation or another service already using port `8091`. This script is not an upgrade tool; if you have an existing setup, back up your content and configuration first.

---

## 💾 Using Content on an SSD

To serve your archive from an external SSD, update the `content_dir` value in `/etc/bilgikutusu-plus/config.json` with the mount path of your SSD folder:

```json
{
  "content_dir": "/mnt/BilgiKutusu"
}
```

* Interface shortcuts recognize the folder names `Haritalar`, `EgitimVideolari`, `Tarim`, and `Balikcilik`. If you also want the sample files visible on the SSD, copy them into these folders manually.
* Ensure the service user has **read and execute** permissions on the SSD directories.
* Restart the service to apply your changes:

```bash
sudo systemctl restart bilgikutusu-plus
```

> [!CAUTION]
> **Security & Privacy:** All accessible files in the selected directory become visible to anyone on the local network. There is no user login or password protection; use only on **trusted local networks**. Do not place personal or sensitive data in the shared directory, and do not expose port `8091` to the internet. The web interface is read-only (it does not upload, delete, or modify files).

---

## ✅ Status Check & Tests

To check the running status of the service and run the unit test suite:

```bash
# View service status
bash durum.sh

# Run automated unit tests
python3 -B -m unittest discover -v
```

The test suite verifies file access, download streaming, HTTP media byte-ranges, Turkish character filenames, configuration validation, hidden file blocking, and directory traversal protection. See [Test Notes](Test-Notlari.md) for further details.

---

## 🤝 Contributing

You can use the repository's **Issues** tab for bug reports and feature suggestions, or submit a **Pull Request** for code improvements.

* When contributing content, always specify the source and copyright/sharing license.
* Never include personal data, passwords, or API keys in your submissions.

Development Team: [Bilikon-Project](https://github.com)

---

## ⚖️ License

This software is provided under the **Free and Non-Commercial Use License 1.0**. The source code may be inspected; terms of use and redistribution are detailed in the [LICENSE](LICENSE) file. Commercial use requires written permission *(this license is not an OSI-approved open-source license)*.

The original license notice of the underlying **BilgiKutusu Go** archive is preserved in [Go-Kaynak-Lisansi.txt](Go-Kaynak-Lisansi.txt). Third-party media and template files are subject to their respective licenses.

---

<div align="center">

**BilgiKutusu Plus · Offline Access to Knowledge**  
[🇹🇷 Türkçe](README-tr.md) · [🇺🇸 English](README.md) · [Bilikon-Project](https://github.com)

</div>
