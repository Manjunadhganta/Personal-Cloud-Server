# Why I Built This

[← Back to README](../README.md)

---

## The Capstone That Started It All

My B.Tech capstone project was a **credit-card-sized NAS device** — a minimal, portable storage unit operating entirely over IP. No graphical OS, no bloat. Plug it into a network and push or pull files from any device on the same subnet. The goal was to prove that functional networked storage didn't need expensive hardware or cloud subscriptions.

It worked. But it had clear limitations: no remote access, no application layer, no services running alongside storage, no resilience after power loss.

That project left me with one question I couldn't let go:

> *What if I took that same philosophy — own your infrastructure, control your data — and built something that could actually run my digital life?*

---

## Problems With Commercial Cloud

| Pain Point | Commercial Cloud | This Server |
|---|---|---|
| Cost | Monthly subscription forever | One-time hardware cost |
| Privacy | Data on third-party servers | Data stays at home |
| Storage limits | Hit limits, pay more | Expand your own drives |
| Control | Subject to policy changes | You own every layer |
| Local speed | Throttled by upload bandwidth | Full local network speed |
| Learning | Black box | You understand every component |

---

## What I Wanted to Learn

This was never just about having cheap storage. I wanted to understand how modern infrastructure actually works:

- How does a VPN route encrypted traffic across the public internet without opening firewall ports?
- What does it take to keep a server stable after power cuts and network drops?
- How do you design a system that recovers itself without you touching it?

Every problem I hit taught me something. This documentation exists so you can understand those lessons too.

---

[Next → Hardware](Hardware.md)
