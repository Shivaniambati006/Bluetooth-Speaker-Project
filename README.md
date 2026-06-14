# 🔊 Bluetooth Speaker Project
### *A sleek, sustainable, and loud-enough-to-wake-your-roommates DIY portable speaker — built from scratch.*

![Hardware](https://img.shields.io/badge/Hardware-Audio%20Electronics-red?style=flat-square&logo=circuitverse)
![CAD](https://img.shields.io/badge/CAD-PTC%20Creo-005BAC?style=flat-square)
![Material](https://img.shields.io/badge/Material-Eco%20MDF-4CAF50?style=flat-square)
![Power](https://img.shields.io/badge/Power-USB%20%7C%209V%20%7C%20Li--ion-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)
![Vibe](https://img.shields.io/badge/Vibe-Immaculate-blueviolet?style=flat-square)


## 📽️ Demo

<div align="center">

<!-- 🎬 DROP YOUR VIDEO / GIF HERE -->
<div align="center">
  <a href="https://www.youtube.com/shorts/TSqEFNRKAfc">
    <img src="https://i.ytimg.com/vi/TSqEFNRKAfc/maxresdefault.jpg" alt="DIY Portable Bluetooth Speaker Project Demo" width="600" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);">
  </a>
</div>

*▶️ Click the thumbnail above to watch it in action — yes, it actually plays music.*

</div>


## Features & Highlights

No off-the-shelf shortcuts. Every component was chosen, wired, and validated by hand.

- **Triple Power Flexibility** — Runs on USB 5V, a 9V DC adapter, OR a 3.7V Li-ion cell boosted to stable system voltage. Bring it anywhere.
- **Low-Power Efficiency** — The **PAM8403 Class-D amplifier** hits >80% efficiency. Less heat, more music, longer battery life.
- **Eco-Friendly by Design** — The enclosure is **3mm recyclable MDF**, laser-cut with press-fit joints. No screws. Minimal adhesive. Fully disassemble-and-repair-able.
- **Wireless Audio** — Stable Bluetooth pairing across iOS, Android, and PC — because cables are so 2005.
- **Modular Internals** — Every electronic module is swappable. One bad component ≠ a dead speaker.

## Circuit & Assembly

### The Signal Chain

Here's how sound travels from your phone to your ears:

```
📱 Your Phone (Bluetooth)
        │
        ▼
🎵 Bluetooth Audio Module   ← wireless audio receiver
        │
        │   Audio Signal (L + R channels)
        ▼
🔊 PAM8403 Class-D Amplifier   ← the muscle (3W × 2ch, filterless)
        │               │
        ▼               ▼
  Speaker LEFT     Speaker RIGHT
    ( + / − )        ( + / − )

⚠️  POLARITY MATTERS. Flip a terminal and you get phase cancellation — 
    which sounds like your speaker is whispering and arguing with itself.
```

### Wiring Checklist

| Step | Connection | Notes |
|---|---|---|
| 1 | Bluetooth Module `OUT` → PAM8403 `IN` | Match L/R channels |
| 2 | PAM8403 `OUT+` / `OUT−` → Speaker terminals | Strict polarity — double-check before powering on |
| 3 | Power source → PAM8403 `VCC` / `GND` | USB 5V, 9V regulated, or boosted Li-ion |
| 4 | Shared `GND` plane | Bluetooth module + amp on same ground — avoids 50Hz hum |

> **Pro tip:** Solder the speaker wires last. Test signal path first with no load attached.

### Enclosure Design

The box is as engineered as the electronics inside.

- **Software:** PTC Creo Parametric — full parametric CAD, dimension-table driven
- **Material:** 3mm Eco-Friendly MDF (recyclable, machinable, and surprisingly good for acoustics)
- **Fabrication:** CNC Laser Cutting — ±0.1mm tolerance on panel edges
- **Joints:** Press-fit tab-and-slot geometry — no screws, no glue mess, structurally rigid
- **Component Bays:** Dedicated cutouts for the amp PCB, Bluetooth module, speaker cones, and power port — everything sits exactly where it should

## Testing & Results

We didn't just plug it in and hope for the best. Here's the full test log:

| Test | Result | Notes |
|---|---|---|
| **Bluetooth Pairing** | ✅ Pass | Stable connection on iOS, Android, and Windows laptop. No re-pairing needed on reconnect. |
| **Audio Quality — Mid Volume** | ✅ Pass | Clear, well-defined sound across vocal and mid-range frequencies. Low noise floor. |
| **Audio Quality — Max Volume** | ⚠️ Marginal | Slight harmonic distortion at peak output — expected PAM8403 clipping behavior at supply voltage ceiling. |
|  **USB 5V Power Rail** | ✅ Pass | Stable operation with zero rail sag under sustained audio load. |
| **9V DC Adapter Rail** | ✅ Pass | Clean regulated 5V post-conversion. Thermal performance within spec. |
| **Li-ion Boosted Rail** | ✅ Pass | Boost converter held 5.0V stable from 4.2V → 3.5V cell discharge curve. |
| **Enclosure Integrity** | ✅ Pass | Press-fit joints held rigid under vibration loads from both speakers. No panel shift. |

## Skills Gained

This project wasn't just a speaker. It was a crash course in real hardware engineering:

- **Circuit Design & Soldering** — Hand-soldered signal path with polarity discipline and clean ground referencing
- **Parametric CAD (PTC Creo)** — Full enclosure modeled from spec to fabrication-ready DXF export
- **Laser Cutting & DFM** — Press-fit joint design, kerf compensation, and tolerance-aware panel layout
- **Power Electronics** — Boost converter integration, multi-rail architecture, and supply decoupling
- **Hardware Troubleshooting** — Diagnosed audio hum, rail sag, and phase issues through systematic testing
- **Technical Documentation** — Wiring protocols, test matrices, and CAD assembly documentation

## 🚀 Applications & Future Upgrades

### What It's Good For Right Now
- 🎵 Desk / workstation audio setup
- 🏕️ Portable outdoor speaker (battery mode)
- 📚 Educational electronics demonstration
- 🎓 Portfolio-worthy hardware build

### The Roadmap (a.k.a. the "Version 2.0 Wishlist")

- [ ] **Rechargeable Battery Integration** — TP4056 Li-ion charging IC + protection circuit (overcharge, over-discharge, short-circuit guard)
- [ ] **Hands-Free / Voice Assistant** — MEMS microphone + Voice Assistant Gateway API passthrough
- [ ] **Music-Synced RGB Lighting** — Addressable LED matrix synchronized to audio amplitude envelope in real time

*PRs welcome if you build any of these first.*

## Team & References

### Team

Built collaboratively with a focus on iterative design, shared troubleshooting, and mutual debugging sessions at 11pm.

| Role | Name |
|---|---|
| **Team Lead & Hardware Design** | Shivani Ambati |

📌 Read the full project write-up: [*"Teamwork & Innovation in Bluetooth Speaker Project"* — Shivani Ambati](https://www.linkedin.posts/shivani-ambati-268a56288_teamwork-innovation-bluetoothspeaker-activity-7206369769371889664-RgLy?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEXsNvABktqRTMACRZbMmkarBZ4V_Mrxd_8)

### References

1. **PAM8403 Datasheet** — Diodes Incorporated. *PAM8403: 3W Filterless Class-D Audio Amplifier.* [diodes.com](https://www.diodes.com/assets/Datasheets/PAM8403.pdf)
2. **Laser Cutting MDF Guide** — Instructables Community. *How to Laser Cut MDF: Settings, Tolerances & Finishing.* [instructables.com](https://www.instructables.com)
3. **PTC Creo Parametric** — PTC Inc. *Creo Parametric CAD Software.* [ptc.com/creo](https://www.ptc.com/en/products/creo)

## 🏁 Get Started

Want to build one yourself? Clone the repo and dig in:

```bash
git clone https://github.com/yourusername/bluetooth-speaker.git
cd bluetooth-speaker
```

Inside you'll find:
- 📁 `/cad` — Creo source files and DXF panel exports
- 📁 `/docs` — Wiring diagrams, BOM, and assembly notes
- 📁 `/media` — Project photos and demo footage

---

## 📄 License

This project is licensed under the **MIT License** — use it, remix it, build on it. Just don't forget to give it a ⭐ if it helped you.

<div align="center">

*Built with solder, sawdust, and an unhealthy amount of coffee. *

**[Shivani Ambati](https://github.com/ShivaniAmbati)** · Embedded Systems · Firmware · Hardware Design

</div>
