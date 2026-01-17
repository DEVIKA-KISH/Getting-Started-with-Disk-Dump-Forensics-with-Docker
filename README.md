> **learning-disk-dump**
> *Hands-on practice with disk acquisition, Docker-based forensic tools, and image analysis*

---

# Learning Disk Dump & Forensics with Docker

This repository documents how to get stareted with **disk acquisition and analysis** using a **custom Kali Linux Docker container** for memory and storage forensics.

📁 Reference Assignment: [Assignment-1.pdf](./Assignment-1.pdf)

---

## 🔧 Tools Used
- 🐳 **Docker Desktop**
- 🐚 **Kali Rolling (Docker image)**
- 🛠️ `foremost`, `testdisk`, `nmap`, `binwalk`, `pytsk3`, `yara`, `pandas`
- 📦 Python environment for forensic scripting

---

## 🚀 What I Did

### 1. 🔨 Built a Custom Docker Image
- Based on Kali Rolling
- Installed forensic tools via `apt-get` and `pip3`
- Built using:
```bash
docker build -t cyber-threats .
````

### 2. 🐳 Verified the Tools in the Container

Tools installed and confirmed working:

```bash
foremost -v
testdisk -v
nmap --version
binwalk -h
pip show pytsk3 yara-python
```

📸 *Screenshots available in [Assignment-1.pdf](./Assignment-1.pdf), page 2.*

---

### 3. 🧪 Acquired a USB Disk Image

Steps performed:

* Ran `lsblk` to verify the attached USB
* Used `wmic diskdrive list brief` in PowerShell to identify the device ID
* Mounted USB drive with read/write access inside Docker container
* Created a raw disk image using `dd`:

```bash
dd if=/dev/sdd of=~/workspace/Disk_image-Kishor_with_image.dd bs=4M status=progress
```

📸 *See screenshots on page 4 of [Assignment-1.pdf](./Assignment-1.pdf)*

---

## 📌 Learning Outcomes

* ✅ Built a reproducible forensic lab with Docker
* ✅ Understood basic acquisition steps using `dd`, `mount`, and `lsblk`
* ✅ Practiced validating and running CLI forensic tools in a contained Kali environment
* ✅ Learned proper disk identification via `wmic` and partition handling with `fdisk`

---

## 🧠 Next Steps

* Explore analysis with Autopsy and Sleuth Kit
* Automate container setup via Dockerfile
* Perform integrity checks (e.g., SHA256 hash comparisons)
* Simulate and detect file system anomalies

---


## 🙋‍♀️ Author

**Devika Kishor**
Graduate Student in Cybersecurity @ Florida Institute of Technology


## ⚠️ Disclaimer

All tools and methods demonstrated here are for **educational and ethical** use only. Do not attempt unauthorized access to systems or data.

```
