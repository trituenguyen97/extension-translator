# Enterprise Meeting Caption Translator (Browser Extension)

> **Enterprise-Deployable Side-Panel Meeting Live Translator & Transcription Suite for Google Chrome & Microsoft Edge**  
> *A grant-seeking, open-source enterprise productivity portal delivering sub-second speech translation, zero-trust BYOK privacy, and seamless fleet deployment via GPO & Microsoft Intune.*

[![Browser Support](https://img.shields.io/badge/Browsers-Google%20Chrome%20%7C%20Microsoft%20Edge-4285F4.svg?logo=googlechrome)](README.md)
[![Deployment](https://img.shields.io/badge/Fleet%20Deploy-GPO%20%7C%20Intune%20%7C%20Registry-0078D6.svg?logo=windows)](docs/)
[![AI Engine](https://img.shields.io/badge/Engine-Google%20Gemini%20Live-4285F4.svg?logo=google)](https://ai.google.dev/)
[![Security](https://img.shields.io/badge/Security-BYOK%20%7C%20Zero%20Data%20Retention-success.svg)](README.md)
[![Extension ID](https://img.shields.io/badge/Extension%20ID-anflamknalpoacapofekflmndbkblkjl-purple.svg)](https://github.com/trituenguyen97/extension-translator/releases/tag/dist)

---

## 🌟 Executive Summary & Pitch

Enterprise adoption of real-time meeting translation faces major friction from IT security and browser compliance:
1. **Public Web Store Bottlenecks:** Public extensions on the Chrome Web Store often leak sensitive audio to untrusted intermediary backend servers, failing corporate data residency and SOC2 reviews.
2. **IT Fleet Deployment Overhead:** Distributing custom internal tools to thousands of employee machines usually requires manual side-loading, developer mode warnings, or cumbersome manual installs.
3. **Multi-Meeting Fragmentation:** Employees switch constantly between Google Meet, Microsoft Teams Web, Zoom Web, and Slack Huddles, requiring a universal, non-intrusive side-panel translation experience.

**Enterprise Meeting Caption Translator** provides an **enterprise-ready browser extension distribution portal** designed for automated fleet deployment via Windows Group Policy (GPO) and Microsoft Intune. Featuring a dedicated browser Side Panel, it streams tab loopback or microphone audio directly to Google Gemini Live for sub-second speech-to-speech translation, realtime transcriptions, and rolling meeting minutes—operating under a strict **Bring-Your-Own-Key (BYOK) zero-data-retention security architecture**.

```
       ┌────────────────────────────────────────────────────────┐
       │             Enterprise IT Fleet Management             │
       │                                                        │
       │   Active Directory GPO / Microsoft Intune Policy       │
       │   Auto-Update Schema: `update.xml` via GitHub Releases │
       └───────────────────────────┬────────────────────────────┘
                                   │ Force-Install Extension CRX
                                   ▼
       ┌────────────────────────────────────────────────────────┐
       │             Chrome / Edge Browser Side Panel           │
       │                                                        │
       │   Google Meet • MS Teams Web • Zoom • Slack Huddles    │
       │   • Capture: Tab Audio Loopback OR Local Microphone    │
       │   • Security: Employee-owned Gemini API Key (BYOK)     │
       └───────────────────────────┬────────────────────────────┘
                                   │ Direct Secure TLS Stream
                                   ▼
       ┌────────────────────────────────────────────────────────┐
       │             Google Gemini Live Cloud Engine            │
       │   • Streaming Speech Recognition (STT)                 │
       │   • Real-Time Multilingual Translation                 │
       │   • Studio Voice Synthesis (Gapless TTS)               │
       │   • Rolling Markdown Meeting Notes & Action Items      │
       └────────────────────────────────────────────────────────┘
```

---

## 🚀 Key Features & Enterprise Capabilities

### 1. Zero-Trust Security & Sovereign BYOK Architecture
- **Bring Your Own Key (BYOK):** Every user configures their personal or corporate Google AI Studio API key. The extension binary contains zero baked-in API credentials, eliminating credential leakage risks.
- **Zero Intermediary Servers:** Audio streams and translated text flow directly between the user's browser client and Google's encrypted API endpoints via TLS. No developer proxy or centralized telemetry server ever intercepts meeting discussions.

### 2. Universal Meeting Side-Panel Integration
- Runs natively within the browser's persistent **Side Panel** without obscuring video feeds or presentation decks.
- Compatible across all browser-based conferencing platforms: **Google Meet**, **Microsoft Teams Web**, **Zoom Web**, **Cisco Webex**, and **Slack Huddles**.
- Flexible input routing: switch dynamically between **Tab Audio Loopback** (hearing remote attendees), **System Microphone** (local speaker), or **Dual Ingestion**.

### 3. Gemini Live Multimodal Full-Duplex Pipeline
- **Real-Time Streaming Translation:** Sub-second speech recognition and translation across Japanese, Vietnamese, English, Korean, and Chinese.
- **Auditory Feedback (TTS):** Streams studio-quality synthesized speech directly through browser audio nodes.
- **Autonomous Meeting Summarization:** Automatically distills lengthy discussions into structured Markdown executive minutes, decision logs, and follow-up action items.

---

## 🏢 Enterprise IT Deployment Guide (GPO / Intune)

For corporate fleet distribution across managed Windows machines:

### Option A: 1-Click Batch Installer (Local Administrator)
1. Download **`apply-policy.bat`** from the latest [GitHub Release (`dist`)](https://github.com/trituenguyen97/extension-translator/releases/tag/dist).
2. Right-click and run as Administrator. The script registers the enterprise force-install extension registry keys.
3. Restart Microsoft Edge or Google Chrome. The extension appears automatically with the *"Installed by your organization"* policy badge.

### Option B: Group Policy (ADMX) / Microsoft Intune
Push the force-install policy string to target endpoints:
- **Microsoft Edge Policy:** *Configure the list of force-installed extensions* (`ExtensionInstallForcelist`)
- **Google Chrome Policy:** *Configure the list of force-installed apps and extensions* (`ExtensionInstallForcelist`)
- **Policy Value:**
  ```text
  anflamknalpoacapofekflmndbkblkjl;https://github.com/trituenguyen97/extension-translator/releases/download/dist/update.xml
  ```

Endpoints automatically check `update.xml` and auto-update whenever a new CRX version is published to GitHub Releases.

---

## ⚡ User Quick Start Guide

1. Open Microsoft Edge or Google Chrome.
2. Click the **Caption Translator** icon in the browser toolbar to open the **Side Panel**.
3. Click the ⚙️ **Settings** tab and paste your **Gemini API Key** (generate from [Google AI Studio](https://aistudio.google.com/apikey)).
4. Select your audio source (🎤 Microphone or 🔊 Meeting Tab Audio) and select your target translation language.
5. Click **Start Session**. Real-time subtitles and streaming voice translation begin immediately.

---

## 🎯 Startup Vision, Grant Objectives & Roadmap

Enterprise Meeting Caption Translator provides the missing enterprise delivery vehicle for high-performance generative AI. We are seeking enterprise grants, cloud partnerships, and seed funding to scale institutional deployments.

### Planned Resource Allocation

```
                   ┌───────────────────────────────────────┐
                   │        Target Grant Allocation        │
                   ├──────────────────┬────────────────────┤
                   │ Central License  │                    │
                   │ & Billing Vault  │        40%         │
                   ├──────────────────┼────────────────────┤
                   │ Chrome Web Store │                    │
                   │ Enterprise Audit │        25%         │
                   ├──────────────────┼────────────────────┤
                   │ Security & SOC2  │                    │
                   │ Compliance Pass  │        20%         │
                   ├──────────────────┼────────────────────┤
                   │ macOS / Safari   │                    │
                   │ Extension Port   │        15%         │
                   └──────────────────┴────────────────────┘
```

1. **Enterprise Identity & Token Quota Gateway (40%):** Building an optional corporate proxy gateway allowing IT departments to centrally manage departmental Gemini quota pools without exposing individual API keys to end users.
2. **Official Web Store Enterprise Auditing (25%):** Completing formal Chrome Web Store enterprise developer certification and CASA (Cloud Application Security Assessment) tier checks.
3. **Enterprise SOC2 & Data Residency Compliance (20%):** Formal third-party penetration testing and cryptographic verification of zero-retention policies.
4. **Safari & Firefox WebExtension Compatibility (15%):** Porting the Side Panel architecture to Safari (macOS/iPadOS) and Firefox ESR.

### Grant Fit
- **Google Cloud for Startups Program** (Showcasing Gemini Live WebExtensions)
- **Enterprise Productivity & Future-of-Work Grants**
- **Open Source Security & Zero-Trust Technology Initiatives**

---

## 🤝 Contact & Enterprise Partnerships

We are actively partnering with enterprise IT administrators and welcome grant foundation discussions:

- **Founder & Maintainer:** Tri Tue Nguyen ([@trituenguyen97](https://github.com/trituenguyen97))
- **GitHub:** [https://github.com/trituenguyen97/extension-translator](https://github.com/trituenguyen97/extension-translator)
- **Deployment Inquiries:** Please open an issue or reach out via GitHub profile.
