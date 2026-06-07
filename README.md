# ᚱ RavenMiner HQ — NerdQAxe+ Dashboard
## *v5.9.2.0 · Thurisaz · The Thorn That Guards the Threshold*

> *"The raven flies not for glory, but for truth. What Huginn sees, Muninn remembers."*

---

```
 ᚠ ᚢ ᚦ ᚨ ᚱ ᚲ ᚷ ᚹ ᚺ ᚾ ᛁ ᛃ ᛇ ᛈ ᛉ ᛊ ᛏ ᛒ ᛖ ᛗ ᛚ ᛜ ᛞ ᛟ
```

---

## What Is This?

**RavenMiner HQ** is a real-time monitoring dashboard for the **NerdQAxe+** Bitcoin ASIC miner — built by a Son of Odin, for those who prefer their tools to carry the weight of the old runes.

This is not a thin wrapper. This is a fully animated, Norse-themed, living instrument panel — rendered in Python with Tkinter, watching your miner breathe through its REST API. It displays hashrate, temperatures, voltages, share counts, best difficulty, pool status, ping latency, fan speed, WiFi signal strength, and BTC price. It alerts you. It pulses like a heart. It shows you the Vegvísir so you never lose your way, and the Valknut so the worthy are always remembered.

Every version is named for a rune of the Elder Futhark. This version answers to **Thurisaz** — the thorn, the giant, the force that holds chaos at the gate.

---

## ✦ Features

- **Real-time hashrate** display with animated Valknut watermark and shimmer effects
- **ASIC & VR temperature gauges** with arc-style canvas rendering and warn/crit thresholds
- **Input voltage & current gauges** with rolling-average smoothing
- **Core voltage (mV)** live display
- **Best Difficulty tracker** with flanking Elder Futhark rune animation
- **Shares OK / Shares BAD** counters with rejection-rate percentage
- **Pool uptime & URL** display
- **Network ping ECG** — oscilloscope-style live latency graph
- **WiFi RSSI radar** — animated polar signal canvas
- **Fan speed & RPM** with animated fan blade rendering
- **BTC/USD price ticker** via CoinGecko (background thread, no blocking)
- **Hashrate history bar graph** (200-bar rolling window)
- **Right-click any gauge** to open a floating history graph window
- **Ntfy.sh webhook alerts** — overheat, low hashrate, block found, rejected spike, milestones
- **Miner reboot control** — slider-guarded with 2-second hold confirmation
- **Settings panel** — all miner config fields editable in-app
- **Source code viewer** — built-in with syntax highlighting and search
- **System tray** integration with Windows balloons
- **Startup WAV** — the miner salutes you when it wakes
- **Vegvísir watermark** — the Norse compass watches from the centre panel
- **Elder Futhark rune cycling** on Best Diff flanks, top bar, and version naming
- **Huginn & Muninn** raven heads in the header — Thought and Memory guard the threshold

---

## ⚙️ Requirements

- Python 3.10+
- `pip install -r requirements.txt`
- A running **NerdQAxe+** (or compatible NerdAxe variant) on your local network
- Windows 10/11 recommended for tray and WAV support (Linux/macOS functional, minus tray)

See [REQUIREMENTS.md](REQUIREMENTS.md) for full dependency details.

---

## 🚀 Quick Start

See [INSTRUCTIONS.md](INSTRUCTIONS.md) for the full setup walkthrough.

**Short path:**
```bash
git clone https://github.com/Raven-Black00/NerdQAxe-Dashboard.git
cd NerdQAxe-Dashboard
pip install -r requirements.txt
python Ravenminer_HQ_5.9.2.0_Thurisaz.py
```

On first launch, click **⚙ Settings**, enter your miner's IP address, save, and the dashboard awakens.

---

## 🗂️ File Structure

```
NerdQAxe-Dashboard/
├── Ravenminer_HQ_5.9.2.0_Thurisaz.py   ← Main application
├── ravenminer.json                       ← Miner config (auto-created)
├── ravenmineralerts.json                 ← Alert/webhook config (auto-created)
├── requirements.txt                      ← Python dependencies
├── README.md                             ← You are here
├── INSTRUCTIONS.md                       ← Setup & usage guide
├── CHANGELOG.md                          ← Full version history
├── REQUIREMENTS.md                       ← Dependency manifest
└── HISTORY.md                            ← The saga of how this was forged
```

---

## 🔗 Links

- **GitHub:** [Raven-Black00/NerdQAxe-Dashboard](https://github.com/Raven-Black00/NerdQAxe-Dashboard)
- **Contact:** sonofgrimnir@outlook.com
- **NerdAxe Project:** [github.com/BitMaker-hub/NerdAxe](https://github.com/BitMaker-hub/NerdAxe)

---

## ᛟ License

MIT License — forge freely, credit the smith.

---

```
  ᚹ ᛟ ᛞ ᛖ ᚾ ᛁ ᛜ   —   The crafting of worthy things
```
