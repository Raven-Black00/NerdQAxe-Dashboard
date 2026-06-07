# ᛈ REQUIREMENTS — The Provisions for the Journey
## *RavenMiner HQ v5.9.2.0 · Thurisaz*

> *"A warrior does not march without provisions. Know what you carry before you begin."*

---

## Python Version

| Requirement | Version |
|---|---|
| Python | **3.10 or higher** |

Python 3.10 is the minimum because of structural pattern matching compatibility in dependencies and f-string features used throughout. Python 3.11–3.13 are all confirmed functional.

---

## Core Dependencies

### `requirements.txt`

```
requests>=2.28.0
Pillow>=9.0.0
pystray>=0.19.0
```

### Standard Library (no install needed)

These are part of Python itself and require no `pip install`:

| Module | Purpose |
|---|---|
| `tkinter` | All UI rendering — the entire visual canvas |
| `tkinter.messagebox` | Native dialog boxes (reboot confirm, errors) |
| `threading` | Background polling threads (data fetch, BTC, ping) |
| `time` | Poll intervals, rolling-average cutoffs, epoch timestamps |
| `math` | Arc calculations for gauges, sine curves for animations |
| `os` | Path resolution for config file locations |
| `base64` | Embedded image/WAV decoding (icon, Vegvísir, Valknut, startup sound) |
| `io` | `BytesIO` for in-memory image loading |
| `json` | Config file read/write (`ravenminer.json`, `ravenmineralerts.json`) |
| `sys` | `sys.argv[0]` for frozen-EXE path detection |
| `re` | Syntax highlighting in source code viewer |
| `colorsys` | Hue rotation for hue-velocity-phase colour animation |
| `traceback` | Error detail logging in exception handlers |
| `collections.deque` | Rolling history buffers for all graph data |
| `webbrowser` | Opens GitHub URL and mailto links |
| `logging` | Module-level logger for warning/error output |
| `socket` | TCP ping implementation |
| `random` | Lightning animation randomness |
| `datetime.timedelta` | Uptime formatting (days/hours/minutes/seconds) |
| `winsound` | Startup WAV playback (Windows only — gracefully skipped on Linux/macOS) |

---

## Third-Party Dependencies Detail

### `requests` ≥ 2.28.0
**Role:** All HTTP communication with the NerdQAxe+ REST API and CoinGecko BTC price endpoint.

- Persistent `requests.Session` reuses TCP connection across polls (saves handshake overhead)
- Used for: `api/system/info`, `api/system/restart`, settings PUT, CoinGecko BTC fetch
- `Connection: keep-alive` header set at session level

```bash
pip install requests
```

---

### `Pillow` ≥ 9.0.0
**Role:** All image operations — icon loading, Valknut animation frames, Vegvísir watermark, raven head images.

- `Image.open()` from BytesIO for base64-embedded assets
- `Image.LANCZOS` resampling for high-quality scaling
- `ImageTk.PhotoImage` bridge to Tkinter canvas
- PIL supersampling: render at 2× then downscale for crisp anti-aliased watermarks
- RGBA compositing for glow effects and transparency

```bash
pip install Pillow
```

---

### `pystray` ≥ 0.19.0
**Role:** System tray icon on Windows (and supported Linux desktop environments).

- Tray icon with right-click menu: Show, Hide, Quit
- Windows balloon notifications for offline/online transitions
- Gracefully disabled if import fails (non-Windows, missing package)

```bash
pip install pystray
```

> **Note:** On Linux, pystray requires a compatible system tray host (e.g., `gnome-shell` with AppIndicator, or `xfce4-notifyd`). If unavailable, the tray icon silently does not appear — the rest of the app is unaffected.

---

### `PyInstaller` *(build-time only)*
**Role:** Packages the application into a standalone Windows `.exe`.

This is **not** required to run the Python script. Only needed if you want to build a distributable binary using the included `RavenMiner_BUILD_6.0.0.bat`.

```bash
pip install pyinstaller
```

---

## Installing Everything

```bash
pip install -r requirements.txt
```

Or explicitly:

```bash
pip install requests Pillow pystray
```

---

## Platform Notes

| Feature | Windows | Linux | macOS |
|---|---|---|---|
| Core dashboard | ✅ Full | ✅ Full | ✅ Full |
| System tray | ✅ Native | ⚠️ DE-dependent | ⚠️ Limited |
| Startup WAV sound | ✅ Yes (`winsound`) | ❌ Skipped silently | ❌ Skipped silently |
| Zoomed/maximised start | ✅ Yes | ✅ Yes | ⚠️ May vary |
| EXE build (PyInstaller) | ✅ Yes | ✅ Linux binary | ✅ macOS app |

---

*The provisions are few. The journey demands much. Pack well, and the ravens will find you.*
