# Lessons Learned

[← Back to README](../README.md)

---

## Technical

- **Restart policies aren't set by default** — on an always-on server, every container needs `--restart unless-stopped`. Without it, a single crash becomes a permanent outage you won't notice until you need the service.
- **BIOS power recovery settings matter** — all the software resilience in the world is useless if the machine doesn't boot after a power cut. The "AC Power Recovery" BIOS setting is the first thing to configure on any home server.
- **Static DHCP leases are better than static IPs in the OS** — easier to manage, survives OS reinstalls, and doesn't require touching network config inside the server.
- **`docker inspect` is more reliable than assuming** — always verify that settings like restart policies were actually applied, not just run.
- **Logs are the only debugging tool on a headless server** — `sudo docker logs <container>` became the first thing I check when anything behaves unexpectedly.

---

## About Self-Hosting

- **Reliability is a design choice, not a default.** Every layer — power, network, storage, application — can fail independently. You have to decide what happens at each failure point before it happens.
- **Simple setups are more resilient.** Three applications running cleanly is better than ten running with problems. Start minimal, add only what you actually use.
- **Owning your infrastructure teaches things that managed services actively hide.** Understanding why a restart policy matters, how VPN tunnels work, and what a BIOS power recovery setting does — these aren't just homelab trivia. They're the same concepts that appear in professional DevOps and infrastructure work, just without the abstraction layer.

---

## The Capstone Connection

The original NAS device asked one question: *"can this work?"*

This project asks a harder one: *"how do you make it actually reliable?"*

That second question is where most of the real learning happens — and it never fully stops.

---

[← Future Improvements](Future-Improvements.md) · [Back to README](../README.md)
