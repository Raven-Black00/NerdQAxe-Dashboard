# ᚾ CHANGELOG — The Chronicle of Each Rune Carved
## *RavenMiner HQ · NerdQAxe+ Dashboard*

> *"Each mark upon the wood is a deed done. Each rune is a change that mattered."*

---

## ᚦ v5.9.2.0 — Thurisaz · *The Thorn* · 2026-06-07

**The thorn guards the threshold. This release sharpens the edge.**

### Added
- `HISTORY.md` — the saga of how RavenMiner HQ was forged
- `REQUIREMENTS.md` — full dependency manifest with rune commentary
- Full Norse-themed documentation suite (README, INSTRUCTIONS, CHANGELOG)
- Version naming formally advances to **Thurisaz** (ᚦ), rune of force and protection

### Changed
- Version bumped from `5.9.1.1` (Uruz) → `5.9.2.0` (Thurisaz)
- Documentation fully rewritten with Elder Futhark thematic structure

---

## ᚢ v5.9.1.1 — Uruz · *The Aurochs* · 2026-05-31

**Raw strength. The aurochs does not ask permission.**

### Added
- Best Difficulty flanking rune animation (Elder Futhark cycling on both sides, offset so they never sync)
- `v5.9.1` sine-phase blue breathe pulse on Best Diff display
- Fast red bounce alpha for Best Diff alert state
- `bdreduntil` epoch tracking for red-alert duration
- `lastbdtext` change-detection guard on Best Diff updates

### Fixed
- Best diff reset detection required two consecutive hits to avoid noisy-poll wipes
- Session reset logic (milestone counter, lastbestdiff) correctly clears on reboot/pending-clear

---

## ᛊ v5.9.0 — Sowilo · *The Sun* · 2026-05

**Victory. Light breaks through. The way forward is clear.**

### Added
- Milestone notifications at every 50M best-difficulty crossing (fires multiple if a single poll jumps across several thresholds)
- Rune index 12 (Sowilo) assigned to right Best Diff rune at launch — permanently offset from left
- `lastmilestonenotified` session tracking — resets cleanly on miner reboot

### Changed
- Best Diff display promoted to bright blue (`#00aaff`) from previous GOLD for high visibility
- Milestone alert includes both the threshold crossed and the current best difficulty value

---

## ᛖ v5.8.x — Ehwaz · *The Horse* · 2026-04

**Movement. The partnership between rider and horse — miner and dashboard.**

### Added
- Hashrate shimmer animation (two-pass shimmer with spark positions at 4.00, 5.00, 6.00 TH/s)
- `hrshimmerpos` and `hrshimmerpos2` dual shimmer tracks
- `hrsparks` tuple — spark threshold markers on hashrate display
- ECG-style ping graph replacing the static `ms` label — oscilloscope canvas, 50-point deque
- `pingecgvals` deque (BUG-M2 fix: was a plain list; deque auto-evicts correctly)

### Fixed
- `BUG-M2`: ping ECG used plain list, could grow unbounded — corrected to `deque(maxlen=50)`
- `PERF-3`: ECG canvas caches `Configure` event dimensions to avoid per-frame `winfo` calls

---

## ᛗ v5.7.x — Mannaz · *Humanity* · 2026-03

**The measure of a man — or a dashboard — is in how it handles failure.**

### Added
- Animated bad-share direction arrow (28×48 canvas, animated phase counter)
- `badarrowdir` tracking: −1 = clean (green), +1 = rising bad shares (red)
- `badarrowrefpct` reference percentage when direction last changed
- WiFi RSSI radar canvas — animated polar signal strength display
- `radarrssi` property read by radar canvas each frame

### Fixed
- `PATCH-P1`: alert config now uses thread-safe getter; eliminates lock-bypass race on ntfy sends
- `CR6-BUG-5`: btclock guard added around BTC counter reset on refresh apply

---

## ᛚ v5.6.x — Laguz · *The Lake* · 2026-02

**The lake reflects everything. Still on the surface, deep below.**

### Added
- Uptime + Firmware version stacked in top-right header bar (`v5.6.5`)
- Son Of Odin branding with flanking Huginn/Muninn raven head images in header
- `sooravenl` / `sooravenr` — mirrored raven-head ImageTk objects
- Pool user (stratum username) displayed in bright gold on ping row

### Changed
- Firmware label moved from settings panel to persistent header display
- UPTIME relocated to top bar from centre-right column

---

## ᛜ v5.5.x — Ingwaz · *Fertility / Potential* · 2026-01

**Seeds planted in the dark winter. Features that would bloom.**

### Added
- Hashrate text rendered directly on Valknut canvas — fully transparent overlay (`v5.5.3`)
- `vegcanvas` (Vegvísir background) fills entire centre column via `.place()`
- `vvitemid` — stable canvas item ID for in-place photo update (avoids blank frame on resize)
- Raven pair drawn flanking Vegvísir watermark — gold-glowing silhouettes
- `ravenflashbase` keyed cache — resize-from-PIL-cache avoids repeated LANCZOS operations

### Fixed
- `FIX-FLASH`: `itemconfig` in-place replaces image on Vegvísir resize, eliminating blank-frame flash
- `v5.5.3`: hashrate label no longer creates a separate widget — lives on `valkcanvas` as canvas text

---

## ᛞ v5.4.x — Dagaz · *Breakthrough / Daybreak* · 2025-12

**The turning point. Dawn arrives.**

### Added
- Gauge history popup windows — right-click any gauge to open floating history graph
- `GaugeHistoryWindow` class with full scrolled canvas, glow line rendering, warn/crit band overlay
- 3-pass glow line rendering (haze → bloom → crisp) for history graphs
- Last-value dot on history graph
- Min/max/avg/last stats bar below history canvas
- `v5.4.8`: ECG canvas replaces `ms` label in same row height for ping display

---

## ᛇ v5.3.x — Eihwaz · *The Yew Tree / Endurance* · 2025-11

**The yew lives forever. So should your monitoring.**

### Added
- `v5.3.3`: Violet-pulse state pre-initialised to avoid per-tick `getattr` overhead
- `v5.3.1`: Flanking raven-head images in header (55px height, mirrored)
- Violet pulse animation system for VR temp alert visual
- Frequency OC gauge in right panel with live arc rendering
- `freqhistory` deque for frequency rolling average

---

## ᛈ v5.2.x — Perthro · *The Mystery / Dice Cup* · 2025-10

**You cast the lot. Sometimes fortune, sometimes correction.**

### Added
- `v5.2.14`: Voltage + current rolling averages (`AVGWINDOW`, configurable 1–10s)
- `v5.2.13`: Core voltage rolling average aligned to same window
- `v5.2.12`: Avg window entry widget in bottom bar (orange, `FocusOut`-triggered)
- `v5.2.11`: History deque for voltage, current, core-volt

### Fixed
- `v5.2.8`: Best Diff pulse — sine phase for slow blue breathe + fast red bounce separate paths
- `v5.2.5`: CONNECTION LOST shown immediately on startup (not after first poll timeout)
- `BUG-05`: `updateevent` threading.Event replaces `updatepending` bool — eliminates race on fast refresh

---

## ᛉ v5.1.x — Algiz · *Protection / Elk* · 2025-09

**The elk-sedge cuts the hand that grabs carelessly. The shield holds.**

### Added
- `v5.1.4`: Fan animation speed derived from `fanpct * 0.18` — proportional spin
- System tray icon with Windows balloon notifications
- `setuptray()` method — pystray integration with right-click menu
- Offline → online transition gold pulse
- `livealpha` / `livedir` for LIVE label fade animation

### Fixed
- `PERF-6`: Persistent requests.Session — TCP connection reused across polls
- `STYLE-04`: Pool user label error suppressed gracefully with `STYLE-04` comment

---

## ᛃ v5.0.x — Jera · *The Harvest / Year* · 2025-08

**The cycle completes. What was planted is now gathered.**

### Added
- Valknut watermark animation — multi-frame ImageTk rotation sequence
- `valkframes` list for frame sequence
- Vegvísir background watermark — PIL supersampling at 2× for crisp AA
- `VEGVISIRPILCACHE` — PIL object cached; only resampled on size change
- Startup WAV playback (`STARTUPWAVB64` — base64-encoded WAV in script)

### Changed
- Window starts in `zoomed` state (maximised) on all platforms

---

## ᛁ v4.x — Isa · *Ice / Stillness* · 2025-06

**Stillness before the storm. The foundation hardens.**

### Added
- `v4.0.4`: 10-second rolling average for input current display
- `v4.0.1`: `rebootpending` flag — live pulse and gold pulse stop immediately on reboot initiation
- Settings panel — full miner config editing in-app
- `ravenminer.json` and `ravenmineralerts.json` persistent config
- Reboot slider control — enable toggle + 0→100 slide + 2-second hold confirmation

### Fixed
- `CR6-BUG-4`: Reboot POST failure now logs warning instead of crashing on dead label lambda

---

## ᚺ v3.9.x — Hagalaz · *Hail / Disruption* · 2025-04

**Hail destroys, but it also clears. Every bug crushed made something stronger.**

### Added
- `v3.9.9`: Milestone tracking for 50M best-diff crossing — `lastmilestonenotified`
- `v3.9.8`: Pool user displayed on ping row in bright gold
- `v3.9.7`: Best Diff tracker with `lastbestdiff` — session max, never dips
- `v3.9.6`: Refresh floor raised to 0.10s (from 1.0) for snappier response
- `v3.9.5`: Network ping display — large font value, below pool uptime
- `v3.9.3`: Source code viewer window with syntax highlighting + search
- `v3.9.3`: `CodeViewerWindow` class — full-file text widget, keyword/string/comment coloring

### Fixed
- `PATCH-CRASH-1`: Hard quit on Escape disabled — was causing random close
- `BUG-10`: Refresh entry `Return` canonicalised to `FocusOut` path
- `BUG-04`: BTC counter reset now guarded by `btclock`
- `CR5-BUG-2`: `btc`/`btcerror` initialised before first `fetchbtc` completes
- `CR2-PERF-7`: Removed redundant `import time as t`, `import re as re` — module-level imports reused
- `STYLE-03`: `self.cfg` guaranteed early init as empty dict

---

## ᚷ v3.x–v2.x — Gebo · *The Gift* · 2025-01–2025-03

**The gift between equals. The early versions, rough-hewn but true.**

- Initial Tkinter layout with left/centre/right column structure
- Basic hashrate, temperature, and share display
- BTC price polling via CoinGecko
- Pool URL and uptime display
- JSON config file persistence
- Dark purple/gold colour palette established

---

## ᚲ v1.x — Kenaz · *The Torch* · 2024-12

**The first light. The torch that lit the forge.**

- Proof of concept: single-window polling of NerdQAxe REST API
- Raw JSON values displayed in Tkinter labels
- No animation, no history, no alerts — just the data, and the will to make it beautiful

---

*Every rune carved is a change that cannot be uncarved. This log is the living memory of the work.*

```
ᚠ ᚢ ᚦ ᚨ ᚱ ᚲ ᚷ ᚹ ᚺ ᚾ ᛁ ᛃ ᛇ ᛈ ᛉ ᛊ ᛏ ᛒ ᛖ ᛗ ᛚ ᛜ ᛞ ᛟ
```
