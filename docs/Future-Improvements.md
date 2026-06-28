# Future Improvements

[← Back to README](../README.md)

---

- **UPS with graceful shutdown** — connect a UPS via USB and configure `apcupsd` to trigger a clean shutdown when battery drops to 20%, preventing filesystem corruption during power cuts
- **Automated off-site backups** — weekly encrypted snapshots of `ZimaOS-HD/Gallery` and `ZimaOS-HD/Documents` to a cloud provider using `restic`
- **Reverse proxy** — set up Nginx Proxy Manager to use clean URLs like `photos.home` and `music.home` instead of IP addresses and port numbers
- **HTTPS** — Let's Encrypt certificates via Caddy for encrypted local access
- **Monitoring** — Grafana and Prometheus dashboards for CPU usage, RAM, disk I/O, and container health over time
- **Larger storage** — replace the 500 GB HDD with a higher-capacity drive, or add a NAS enclosure for more bays
- **RAID / ZFS** — mirror storage for redundancy once the library grows large enough to matter
- **Immich AI improvements** — explore custom CLIP models for better photo semantic search

---

[← Troubleshooting](Troubleshooting.md) · [Next → Lessons Learned](Lessons-Learned.md)
