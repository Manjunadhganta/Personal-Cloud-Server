# Problems I Faced & How I Solved Them

[← Back to README](../README.md)

> These are real problems I ran into during setup and over weeks of running the server. Not copied from documentation — they happened.

---

## 1. Docker Containers Not Restarting After Power Cuts

**Problem:** When power returned after an outage, the server booted up but the containers (Immich, Navidrome) stayed stopped. I had to SSH in and start them manually every time.

**Cause:** The containers installed through the ZimaOS App Store didn't have an automatic restart policy set by default.

**Fix:** Used SSH to set the restart policy on each container directly:

```bash
# Connect to the server
ssh admin@<your-server-ip>

# Set restart policy for each container
sudo docker update --restart unless-stopped immich_server
sudo docker update --restart unless-stopped navidrome
sudo docker update --restart unless-stopped tailscale
```

`unless-stopped` means Docker will automatically restart the container whenever it stops — including after a reboot — unless you manually stop it yourself.

To verify it was applied:

```bash
sudo docker inspect --format '{{.HostConfig.RestartPolicy.Name}}' immich_server
# Should output: unless-stopped
```

---

## 2. Tailscale Container Exiting After Power Cuts

**Problem:** Even after fixing the restart policy, Tailscale specifically kept exiting after the server rebooted from a power cut. Other containers came back fine.

**Cause:** Tailscale requires the `/dev/net/tun` (TUN) network interface to be available when it starts. During boot, Docker sometimes starts Tailscale before the kernel has fully initialised the TUN device, causing the container to fail immediately.

**Fix:** Manually restarted Tailscale once after each boot. To check and fix:

```bash
# Check if TUN device is available
ls /dev/net/tun

# Manually restart Tailscale if it failed on boot
sudo docker restart tailscale
```

---

## 3. Wake-on-LAN Not Working

**Problem:** Sending a Wake-on-LAN magic packet to the server's MAC address had no effect. The server didn't wake up.

**Cause 1:** Wake-on-LAN was not enabled in the BIOS.

**Fix 1:** On boot, press F2 (or DEL) to enter BIOS → navigate to **Power Management** → enable **Wake on LAN**.

**Cause 2:** After a full power cut (not a soft shutdown), the server still didn't boot automatically when power returned.

**Fix 2:** Found the **"AC Power Recovery"** setting in BIOS (sometimes called "After Power Loss") and changed it from `Last State` to `Power On`. This makes the server boot automatically whenever power is restored, regardless of how it was shut down.

---

## 4. Navidrome Not Picking Up New Music Files

**Problem:** I added new albums to `ZimaOS-HD/Media` but they didn't appear in Navidrome.

**Cause:** Navidrome scans the music folder on a schedule. Files added between scans aren't visible until the next scan runs.

**Fix:** Triggered a manual scan from the Navidrome admin panel:

```
Navidrome UI → Settings → Scan Library → Scan Now
```

For active music imports, temporarily changed the scan interval to every 5 minutes, then set it back to every hour once done.

---

## 5. Immich Taking a Long Time to Start After Reboot

**Problem:** After a server reboot, Immich was unreachable for 3–5 minutes even though Docker showed the container as running.

**Cause:** On first start after a reboot, Immich runs database migrations before it's ready to serve requests. The container reports as "running" but isn't actually ready yet.

**Fix:** Not a real error — just a wait. Immich is ready when you can open the web UI and log in. After the first start, subsequent restarts are much faster because migrations are already done.

---

## 6. Server IP Changing After Router Reboots

**Problem:** After the router rebooted, the server was assigned a different local IP. All bookmarks and app configs that used the old IP stopped working.

**Fix:** Logged into the router admin panel and assigned a **static DHCP lease** — this binds the server's MAC address to a fixed IP address. The router always hands out the same IP to the server, without needing to configure a static IP inside the OS itself.

```
Router Admin → DHCP → Static Leases → Add → [Server MAC address] → [Fixed IP]
```

---

[← Remote Access](Remote-Access.md) · [Next → Future Improvements](Future-Improvements.md)
