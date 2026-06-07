# ᚺ Instructions — The Rites of Awakening
## *RavenMiner HQ v5.9.2.0 · Thurisaz*

> *"Before you call upon the All-Father's ravens, you must first prepare the altar."*

---

## ᛁ — Prerequisites

Before the dashboard can speak, these truths must be established:

1. **Python 3.10 or higher** must be installed on your machine.
   - Download: [python.org/downloads](https://www.python.org/downloads/)
   - Verify: `python --version`

2. **pip** must be available:
   - Verify: `pip --version`

3. **Your NerdQAxe+ miner** must be on your local network and accessible via its HTTP API.
   - Find its IP via your router's DHCP table, or look at the miner's screen.
   - Verify: open `http://<miner-ip>/api/system/info` in a browser — you should see JSON.

4. **Windows 10/11** is recommended for full feature support (system tray, WAV startup sound, `winsound`).
   - Linux/macOS: all core features work. Tray icon and startup sound are gracefully skipped.

---

## ᚢ — Installation

### Step 1 — Clone the Repository

```bash
git clone https://github.com/Raven-Black00/NerdQAxe-Dashboard.git
cd NerdQAxe-Dashboard
```

### Step 2 — Install Dependencies

```bash
pip install -r requirements.txt
```

If you prefer a virtual environment (the prudent path):

```bash
python -m venv venv

# Windows:
venv\Scripts\activate

# Linux/macOS:
source venv/bin/activate

pip install -r requirements.txt
```

### Step 3 — Launch

```bash
python Ravenminer_HQ_5.9.2.0_Thurisaz.py
```

The dashboard will open maximised. You will hear the startup WAV if on Windows. The ravens greet you.

---

## ᚨ — First-Time Configuration

### Setting Your Miner IP

1. Click the **⚙ Settings** button in the right panel.
2. In the `Miner IP` field, enter your miner's IP address (e.g., `192.168.1.105`).
3. Click **Apply** or press **Enter**.
4. The dashboard will begin polling immediately.

Settings are saved to `ravenminer.json` in the same directory as the script.

### Configuring Miner Parameters (Optional)

The Settings panel also exposes:
- **Stratum URL & Port** — your mining pool
- **Stratum Username** — your wallet/worker string
- **Core Frequency (MHz)** — overclocking target
- **Fan Speed** — manual override (or enable Auto Fan)
- **Target Temperature** — PID fan control target
- **Screen flip/invert** — for physical miner display orientation

---

## ᚷ — Alerts & Webhooks (ntfy.sh)

RavenMiner HQ can push alerts to your phone via [ntfy.sh](https://ntfy.sh).

### Setup

1. Install the **ntfy** app on your phone (iOS or Android).
2. Subscribe to a topic of your choosing (e.g., `raven-miner-alerts-alan`).
3. In the **⚙ Settings** panel, enter your topic in the `ntfy Topic` field.
4. Configure thresholds:
   - **Alert Temp (°C)** — ASIC overheat threshold (default 85°C)
   - **VR Alert Temp (°C)** — VR overheat threshold (default 85°C)
   - **Hashrate Alert (TH/s)** — low hashrate threshold (default 0.5 TH/s)
5. Click **Apply**. Alert config is saved to `ravenmineralerts.json`.

### Alert Types
- 🔥 ASIC overheat
- 🟠 VR overheat
- 📉 Low hashrate
- 🏆 Block found
- ⚠️ Rejected share spike
- ✨ Best difficulty milestones (every 50M)

---

## ᛈ — Dashboard Controls

| Control | Action |
|---|---|
| **Right-click any gauge** | Opens floating history graph window |
| **Refresh s** (bottom bar) | Sets the main poll interval (0.10–5.00s) |
| **Graph s** (bottom bar) | Sets the hashrate bar graph refresh rate |
| **Avg s** (bottom bar) | Sets the rolling-average window for voltage/current/core-volt |
| **Ping avg s** (bottom bar) | Sets the ping rolling-average window |
| **⚙ Settings** (right panel) | Opens full settings panel |
| **💀 Reboot** (right panel) | Guarded reboot — enable toggle, slide to 100, hold 2s |
| **`</>` Source** (right panel) | Opens built-in source code viewer with syntax highlight + search |
| **Version label** (top right) | Clickable — opens this GitHub repository |
| **Email label** (top centre) | Clickable — opens mailto link |

---

## ᛏ — Building a Standalone EXE (Windows)

A build script is provided: `RavenMiner_BUILD_6.0.0.bat`

This uses **PyInstaller** to bundle the app into a single `.exe`:

```bat
RavenMiner_BUILD_6.0.0.bat
```

The resulting executable will be in the `dist/` folder.

Requires PyInstaller:
```bash
pip install pyinstaller
```

---

## ᛒ — Troubleshooting

**Dashboard shows `CONNECTION LOST` / all values `--`**
- Verify miner IP in Settings
- Confirm miner is powered on and reachable: `ping <miner-ip>`
- Check your miner's API is responding: `curl http://<miner-ip>/api/system/info`

**No startup sound**
- `winsound` is Windows-only; this is expected on Linux/macOS

**Tray icon missing**
- `pystray` and `Pillow` must both be installed. On Linux, a system tray host may be required.

**Icons appear blank / Vegvísir missing**
- Ensure `Pillow` is installed: `pip install Pillow`

**High CPU usage**
- Raise the **Refresh s** value in the bottom bar to 1.0–2.0 seconds

---

## ᛟ — Config File Locations

| File | Purpose |
|---|---|
| `ravenminer.json` | Miner IP, pool, frequency, fan settings |
| `ravenmineralerts.json` | ntfy topic, alert thresholds |

Both files are created automatically on first launch / first save. They live next to the `.py` file (or next to the `.exe` if compiled).

---

*May Huginn carry your questions and Muninn return with answers.*
