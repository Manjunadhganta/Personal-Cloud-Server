# Software Stack

[← Back to README](../README.md)

---

| Software | Role | Why I Chose It |
|---|---|---|
| **ZimaOS** | Host operating system | Built for home servers; has a clean dashboard and a built-in App Store — no manual Docker setup needed |
| **Docker** | Container runtime | Ships with ZimaOS; each app runs in isolation |
| **Immich** | Photo & video management | Self-hosted Google Photos alternative with mobile backup, face recognition, and AI-powered search |
| **Navidrome** | Music streaming | Lightweight music server; works with any Subsonic-compatible app on phone or desktop |
| **Tailscale** | VPN & remote access | Zero-config WireGuard VPN — connect to the server from anywhere in the world without opening router ports |
| **SSH** | Remote terminal access | Direct terminal access for configuration, troubleshooting, and running commands on the server |
| **Wake-on-LAN** | Remote power control | Boot the server remotely if it's powered off |

---

## On the App Store vs Docker Compose

ZimaOS includes a built-in **App Store** that lets you install applications like Immich, Navidrome, and Tailscale in one click — no manual `docker-compose.yml` required. Behind the scenes, ZimaOS is still running them as Docker containers, but it handles the configuration, volumes, and networking automatically.

All three main applications in this project were installed this way. It's the recommended approach for ZimaOS — simpler, and the containers are visible and manageable directly from the ZimaOS dashboard.

---

[← Hardware](Hardware.md) · [Next → Architecture](Architecture.md)
