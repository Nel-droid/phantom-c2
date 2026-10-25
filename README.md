# PHANTOM — Security Training Framework

Mobile & desktop security awareness training platform with C2 demo capabilities. Built for educational workshops to demonstrate how real threats work.

## Features

- **Real-time device monitoring** — heartbeat beacons, device info collection, network enumeration
- **File browser & exfiltration demo** — browse, upload, and download files from connected devices
- **Remote shell** — execute commands on Android and Windows targets
- **Screen capture & streaming** — live screen view with tap/swipe/text input
- **APK/EXE payload generation** — build agents directly from the dashboard
- **Push notifications** — send messages to connected devices

## Tech Stack

| Component | Technology |
|-----------|------------|
| Server | Flask (Python) |
| Android agent | Kotlin + WorkManager + MediaProjection |
| Windows agent | C (mingw-w64 cross-compiled) |
| Dashboard | Single-page HTML/JS |

## Quick Start

```bash
# Clone
git clone https://github.com/Nel-droid/phantom-c2.git
cd phantom-c2

# Install server dependencies
pip install flask

# Run the server
python server/web_server.py
# Dashboard at http://localhost:8080

# Build the Android APK
# Option A: Android Studio — open the project root and build
# Option B: Command line (requires Android SDK + JDK 21)
./gradlew assembleDebug
```

Edit `app/build.gradle.kts` and set `BEACON_URL` to your server's public URL before building the APK.

For global access, run the server behind ngrok or a Cloudflare tunnel.

## Credits

Based on work by [Bobur Abdugafforov](https://github.com/abdugafforov-bobur).

## Disclaimer

**For educational and authorized security training purposes only.** Do not deploy against targets without explicit consent.
