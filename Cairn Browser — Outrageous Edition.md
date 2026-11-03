# 🧭 Cairn Browser — Outrageous Edition

> **Sovereign, Privacy-First, Zero-Telemetry Chromium Desktop Browser with Bundled Onion Routing & On-Device Local AI.**

[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011%20(x64)-0078D6?style=flat-square&logo=windows)](https://dev-cairn.github.io/)
[![Version](https://img.shields.io/badge/Version-v1.0.1%20Outrageous-9d4edd?style=flat-square)](https://dev-cairn.github.io/)
[![Chromium Core](https://img.shields.io/badge/Chromium-126%2B%20%7C%20Electron%2031-4285F4?style=flat-square&logo=googlechrome)](https://dev-cairn.github.io/)
[![Tor Bundle](https://img.shields.io/badge/Tor%20Bundle-v16.0%20Bundled-7D4698?style=flat-square&logo=torproject)](https://www.torproject.org/)
[![License](https://img.shields.io/badge/License-Proprietary%20%2F%20Sovereign-2ea44f?style=flat-square)](THIRD_PARTY_LICENSES.md)

---

## ⚡ What is the Outrageous Edition?

**Cairn Browser (Outrageous Edition)** is the unconstrained, standalone power-user release built specifically for software engineers, security researchers, and sovereign individuals. 

Free from app-store sandboxing limitations, the Outrageous Edition incorporates an internal Tor network daemon, 100% on-device local AI, and hardware-level anti-fingerprinting shields with zero external software requirements.

---

## 🚀 Core Architectural Highlights

### 🧅 1. Self-Contained Onion Mode (Bundled Tor v16.0)
* **Zero External Dependencies:** Bundles the official, signed **Tor Expert Bundle (v16.0)** directly within the application package. No standalone Tor Browser installation is ever required.
* **Dynamic Ephemeral Port Allocation:** Avoids hardcoded ports (e.g. 9050) by dynamically requesting free local TCP ports from the operating system (`127.0.0.1:0`), preventing port collision crashes.
* **Pluggable Transports:** Bundled `lyrebird.exe` provides out-of-the-box **Snowflake** (WebRTC rendezvous) and **obfs4** bridge transports for automated ISP censorship circumvention.
* **Intelligent Auto-Fallback:** Connects via a fallback chain (`Direct ➔ Snowflake ➔ obfs4`) and automatically remembers the working transport method for accelerated future launches.
* **Strict Anti-Leak Protections:** 
  - Remote DNS resolution (`proxyBypassRules: '<-loopback>'`) prevents local ISP DNS leaks.
  - WebRTC UDP interface shutdown (`disable_non_proxied_udp`) eliminates local and public IP exposure.
  - Ephemeral session partitions (`tor-session-*`) discard all cookies, storage, and socket caches upon session termination or circuit renewal (`SIGNAL NEWNYM`).
* **Zombie Process Prevention:** Launched with `__OwningControllerProcess` and control port `TAKEOWNERSHIP` so Tor self-terminates immediately if Cairn ever closes or crashes.

### 🤖 2. Viola AI — 100% On-Device Local Intelligence
* **Local Hardware Execution:** Executes quantized GGUF weights locally on your CPU/GPU using the high-performance `node-llama-cpp` runtime.
* **True Offline Capability:** Fully functional without an internet connection.
* **Zero Telemetry & Cloud Leaks:** Your prompts, code snippets, and research data are never transmitted to OpenAI, Google, or any cloud API.
* **Rich Markdown & Math:** Streams responses in real time with full KaTeX mathematical rendering and one-click code copy blocks.

### 🛡️ 3. "Blend in the Crowd" Dynamic Anti-Fingerprinting
* **Randomized Farbling Engine:** Injects micro-noise into HTML5 Canvas (`getImageData`, `toDataURL`, `toBlob`), WebGL, and Web Audio APIs.
* **Signature Scrambling Across Reloads:** Generates unique, non-correlatable canvas hashes on every reload (live-verified on BrowserLeaks) without causing visible graphical artifacts.

### ⚡ 4. Native Split View
* View and interact with two tabs side-by-side with fluid dragging and independent scrolling, reloading, and navigation controls.

### 🔐 5. Zero-Knowledge Password Vault & Privacy Lock
* **AES-256-GCM + PBKDF2 (100,000 iterations):** Client-side vault encryption. Master keys never leave your machine's volatile memory.
* **Desktop Privacy Lock (`Ctrl+Shift+L`):** Instantly detaches and obscures all active WebViews behind a biometric/PIN lock screen until authenticated.

### 🧩 6. Triple Chromium Extension Ecosystem
Direct 1-click installations supported across three major stores:
* 🌐 **Google Chrome Web Store**
* 🌐 **Microsoft Edge Add-ons**
* 🌐 **Opera Add-ons Catalog** (with automated header spoofing)

### 📞 7. Encrypted P2P Audio/Video Meetings
* Direct browser-to-browser WebRTC connection using **Trystero**. End-to-end encrypted voice, video, and screen sharing with zero intermediary servers.

### 💾 8. Offline-First SQLite Storage & Clean Lifecycle
* Local browsing history, bookmarks, and downloads reside in a secure SQLite database (`sql.js`) with automated 30-day rolling history pruning.
* **Clean Uninstall:** Uninstalling Cairn cleanly purges `%APPDATA%\cairn`, recovering all local storage and cached models without leaving residual files.

---

## 💻 System Requirements

| Specification | Minimum Requirement | Recommended |
| :--- | :--- | :--- |
| **Operating System** | Windows 10 (64-bit) | Windows 11 (64-bit) |
| **Processor (CPU)** | Intel Core i3 / AMD Ryzen 3 (x64) | Intel Core i5 / AMD Ryzen 5 or higher |
| **System Memory (RAM)**| 4 GB RAM | 8 GB+ (for local AI inference) |
| **Disk Space** | 500 MB (App installation) | 2 GB (with optional local AI model) |

---

## 📦 Available Installers (v1.0.1)

| Package | Filename | Description |
| :--- | :--- | :--- |
| **EXE Installer** | `Cairn Setup 1.0.1.exe` (~378 MB) | Standard interactive 1-click setup with custom directory selection and clean uninstaller. |
| **MSI Installer** | `Cairn 1.0.1.msi` (~378 MB) | Standalone Windows Installer package for system administrators and power users. |

---

## 🛡️ Privacy Manifesto (Zero Telemetry)

Cairn Browser operates strictly under a **Zero-Telemetry Policy**:
1. No browsing history, search queries, or IP addresses are logged.
2. No analytics trackers or telemetry SDKs are embedded in the code.
3. Your vault, tabs, and preferences exist exclusively on your local device.

---

## 👨‍💻 Developer & Attribution

* **Product:** Cairn Browser (`com.cairn.browser`)
* **Developer:** Md Tareq Shah Alam
* **Organization:** Nightstar Labs
* **Website:** [https://dev-cairn.github.io/](https://dev-cairn.github.io/)
* **Third-Party Licenses:** [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md) (Covering Chromium, Tor Project, Lyrebird, Libevent, OpenSSL, SQLite)

---

*Cairn Browser — Take back your digital autonomy.*

