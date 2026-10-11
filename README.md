<div align="center">

<img src="assets/logo.png" alt="Immediate Tool Pro" width="120">

# Immediate Tool Pro

**Android Utility for Windows: ADB & Fastboot, made simple**

![Version](https://img.shields.io/badge/version-0.3.0-3b82f6)
![Platform](https://img.shields.io/badge/platform-Windows-0078d6)
![Python](https://img.shields.io/badge/python-3.12%2B-yellow)
![UI](https://img.shields.io/badge/UI-PySide6-41cd52)

</div>

---

## About

**Immediate Tool Pro** is a Windows desktop utility for Android devices. It gives you a clean graphical interface for common ADB and Fastboot tasks, so you don't have to type commands by hand. Device info, APK install, reboot options, scrcpy, driver installers and root/kernel app installers are all a click away.

The app is built with **Python** and **PySide6** and ships as a single standalone `.exe` that runs from any folder.

## Features

### Device Tools
- **Device Information**: view detailed info of the connected phone (ADB and Fastboot modes)
- **ADB Tools**: restart the ADB server
- **Platform-Tools CMD**: open a command prompt with ADB/Fastboot ready
- **Install APK**: pick any APK and install it on the phone
- **Reboot**: System, Recovery or Bootloader
- **Launch scrcpy**: mirror and control the phone screen from your PC

### Root & Kernel
One-click installers (via `adb install -r`) for:

Root Checker, Magisk, Magisk Delta, Kitsune Mask, KernelSU, KernelSU Next, SukiSU Ultra, APatch, FolkPatch, Shizuku

### Additional Tools
- **Driver installers**: Fastboot, libusbK, USBDK, Qualcomm + MTK, QDLoader 9008
- **Operation History**: see what you did before
- **Error Logs**: quick access to logs for troubleshooting

### Other
- Live device detection with a status indicator (No device / ADB / Fastboot)
- Dark, modern interface
- Background tasks with a progress bar, so the window never freezes
- Built-in log panel for every operation

## Download

Go to the [**Releases**](../../releases) page and download the latest `ImmediateToolPro.exe`. No installation needed. Just run it.

> **Note:** Windows SmartScreen or antivirus may show a warning for unsigned PyInstaller apps. This is a false positive. Click **More info > Run anyway**.

## Requirements

- Windows 10 / 11
- USB cable and an Android phone
- **USB debugging** enabled on the phone (for ADB features)
- Phone drivers installed (use *Additional Tools* if needed)

## How to Use

1. Enable **Developer options > USB debugging** on your phone.
2. Connect the phone to your PC with a USB cable.
3. Open Immediate Tool Pro and click **Detect Devices**.
4. Allow the USB debugging prompt on the phone.
5. Choose a page from the left menu and click the tool you need.

## Build From Source

Requires **Python 3.12+**.

```bash
git clone https://github.com/USERNAME/REPO.git
cd REPO
```

1. Put the Android **platform-tools** zip inside the `platform-tools/` folder.
2. (Optional) Put your APKs in `apks/<App Name>/`, scrcpy zip in `scrcpy/`, and driver installers in `driver_files/<Driver Name>/`.
3. Run **`build_exe.bat`**.
4. The finished **`ImmediateToolPro.exe`** appears next to the bat file.

To run without building:

```bash
pip install -r requirements.txt
python main.py
```

To run tests:

```bash
python -m pytest tests -q
```

## Project Structure

```
main.py  build_exe.bat  requirements.txt
ui/          Main window, theme, popups, support window
core/        Paths, runner, worker, scrcpy, drivers, APK helpers
devices/     ADB, Fastboot, detector, device models
database/    Operation history storage
assets/      Logo and icon
apks/        Root & Kernel app APKs (one folder per app)
scrcpy/      Put scrcpy zip here
driver_files/ Driver installers (one folder per driver)
tests/       Automated tests
docs/        Roadmap
```

## Troubleshooting

Logs are saved in `%LOCALAPPDATA%\ImmediateToolPro\`:

- `immediate_tool.log`: normal errors
- `crash.log`: hard crashes

| Problem | Fix |
|---|---|
| Device not detected | Check cable, enable USB debugging, install drivers, click **Detect Devices** |
| "unauthorized" device | Accept the RSA prompt on the phone screen |
| APK install fails | Read the message in the log panel. It explains the cause (downgrade, older SDK, etc.) |
| ADB not found | Set the platform-tools folder in **Settings** |

## Disclaimer

This tool performs actions that can change your device (reboot, flashing-related modes, root app installs). Use it at your own risk. The developer is not responsible for any damage or data loss. Always back up your data first.

Third-party apps (Magisk, KernelSU, scrcpy, drivers and so on) belong to their respective owners and follow their own licenses.

## Developer

**Nayem Khan**

- Website: [immediate.rf.gd](https://immediate.rf.gd)
- YouTube: [@bengleraptor](https://youtube.com/@bengleraptor)
- TikTok: [@naimbinharun](https://tiktok.com/@naimbinharun)
- Telegram Group: [Join](https://t.me/+mU6PXP7hXR9hN2M1)
- Facebook Group: [Join](https://facebook.com/share/g/1JbRQgSuZz/)
- Proof / Verification: [t.me/nayemroot](https://t.me/nayemroot)

---

<div align="center">

If this tool helped you, give the repo a star.

</div>
