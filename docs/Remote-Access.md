# Remote Access — Worldwide

[← Back to README](../README.md)

---

Here is exactly how the full remote access chain works in this setup:

1. **Tailscale runs on both the server and your phone** — they share a private encrypted network regardless of where they physically are
2. **No port forwarding is needed** on the home router — Tailscale uses NAT traversal (DERP relay nodes as fallback) to punch through firewalls automatically
3. **All traffic is encrypted** end-to-end using WireGuard, the same protocol used in many commercial VPNs
4. **Local access still works** — when you're on the home network, apps use the local IP directly; Tailscale adds zero latency in that case

This means the same app setup on your phone works at home and abroad, with no manual switching between network modes.

---

## Connection Flow

```
Your Phone (anywhere)
        │
        ▼
  Tailscale App
        │  encrypted WireGuard tunnel
        ▼
  Tailscale Network
        │
        ▼
  Tailscale container on server
        │
        ▼
  Immich / Navidrome container
        │
        ▼
  ZimaOS-HD (your files)
```

---

## Key Points

- **No public IP required** — Tailscale handles NAT traversal automatically
- **No dynamic DNS required** — the Tailscale IP (`100.x.x.x`) for your server never changes
- **No open router ports** — your home network stays closed to the public internet
- **Encrypted** — all traffic uses WireGuard encryption end-to-end

---

[← Applications](Applications.md) · [Next → Troubleshooting](Troubleshooting.md)
