# 🖥️ Personal Cloud Server — Built on ZimaOS

> *From a credit-card-sized B.Tech capstone to a full self-hosted server running 24/7, accessible from anywhere in the world.*

---

## 📖 Table of Contents

1. [Introduction](#introduction)
2. [Why I Built This](docs/Why-I-Built-This.md)
3. [Hardware](docs/Hardware.md)
4. [Software Stack](docs/Software-Stack.md)
5. [Architecture](docs/Architecture.md)
6. [Installation & Setup](docs/Installation.md)
7. [Configuring Each Application](docs/Applications.md)
8. [Remote Access — Worldwide](docs/Remote-Access.md)
9. [Problems I Faced & How I Solved Them](docs/Troubleshooting.md)
10. [Future Improvements](docs/Future-Improvements.md)
11. [Lessons Learned](docs/Lessons-Learned.md)

---

## Introduction

Cloud storage is everywhere. Google Drive, OneDrive, Dropbox — they all make it trivially easy to access your files from any device. But every one of them relies on someone else's infrastructure, someone else's servers, and a subscription you keep paying indefinitely. Your data lives on hardware you've never seen, managed by companies whose privacy policies you probably haven't fully read.

That bothered me.

During my final year at VIT Amaravati, I built a capstone project: a **credit-card-sized Network Attached Storage (NAS)** device. No operating system overhead, purely IP-based — it could upload and download files over a network and fit in your pocket. The concept worked. But I knew it could be so much more.

That capstone became the seed of this project.

Today, this server runs **24 hours a day, 7 days a week**, inside my home network, on my own hardware. It hosts personal photo backups, a music streaming service, and secure remote access — all without a single subscription to a third-party cloud provider. From anywhere in the world, I can pull up my photos, stream music, or grab a file — through an encrypted VPN connection that I fully control.

---

## Quick Overview

| Component | Details |
|---|---|
| **Hardware** | Intel Celeron J1900 · 8 GB RAM · 500 GB HDD |
| **OS** | ZimaOS |
| **Applications** | Immich · Navidrome · Tailscale |
| **Remote Access** | Tailscale VPN (WireGuard) |
| **Uptime** | 24/7 |

---

## Repository Structure

```
Personal-Cloud-Server/
├── README.md
├── docs/
│   ├── Why-I-Built-This.md
│   ├── Hardware.md
│   ├── Software-Stack.md
│   ├── Architecture.md
│   ├── Installation.md
│   ├── Applications.md
│   ├── Remote-Access.md
│   ├── Troubleshooting.md
│   ├── Future-Improvements.md
│   └── Lessons-Learned.md
└── screenshots/
    ├── hardware.png
    ├── boot1.png ... boot9.png
    ├── first-boot.png
    ├── login.png
    ├── appstore.png
    ├── appinstalled.png
    ├── ssh-terminal.png
    ├── immich.png
    └── navidrome.png
```

---

*Manjunadh Reddy Ganta*
