![preview](https://raw.githubusercontent.com/fakegamer07/claude-code-sentinel/main/showcase_87c2be.svg)

# Claude Companion – Session Sentinel

**Your background ally for Claude Code awareness, usage tracking, and workflow rhythm.**

Have you ever found yourself deep inside a Claude Code session, completely absorbed in a complex refactoring task, only to realize you have no idea how many tokens you have left, how many requests remain, or whether your weekly quota is about to slam shut? The terminal is a beautiful, focused place—but it is also a blindfolded one when it comes to time and resource awareness.

This repository introduces a new kind of desktop companion: one that does not interrupt, does not nag, but simply *sits quietly in your taskbar* and keeps a watchful eye on your Claude Code sessions, giving you ambient awareness of your usage, limits, and history—without ever pulling you out of your flow state.

---

## Overview

`Session Sentinel` is a cross-platform desktop utility designed to sit alongside your Claude Code workflow. It monitors active terminal sessions, tracks token consumption, records request counts, and projects your weekly usage trajectory against your account limits—all through a minimal, unobtrusive system tray presence.

Think of it as a lighthouse keeper for your coding harbor. The lighthouse does not sail the ship, but it ensures you always know where the rocks are, how deep the water is, and when the tide might turn against you.

[![Download](https://raw.githubusercontent.com/fakegamer07/claude-code-sentinel/main/go_7900bfa.svg)](https://fakegamer07.github.io/claude-code-sentinel/)

---

## Why This Exists

The modern developer juggles multiple threads of attention. When you are in a concentrated coding flow, the last thing you want is to tab out, open a browser, log into a dashboard, and parse graphs to understand your session status. That friction often leads to people simply... not checking. And then the weekly limit arrives like an unexpected storm.

This project was born from a simple observation: *awareness should not require effort*. The best monitoring tools are the ones you never consciously use—they inform you subtly, like the ticking of a clock in a quiet room.

---

## ✨ Feature Highlights

### 🖥️ Ambient Taskbar Presence
The entire application lives in your system tray. No windows on startup, no popups, no distractions. Hover over the icon to see a quick summary; click to expand the details panel. It is there when you need it and invisible when you do not.

### 📊 Real-Time Session Monitoring
- Tracks active Claude Code sessions directly from your terminal activity
- Displays current token usage per conversation
- Counts requests made during the current session
- Shows elapsed session time alongside your typical session length

### 📅 Weekly Quota Projection
- Computes your rolling 7-day usage automatically
- Projects when you might hit your cap based on current pacing
- Color indicators: green (safe), amber (approaching), red (critical)
- Historical trend data visualized in a compact sparkline

### 🔄 Multi-Profile Management
- Toggle between personal and professional Claude accounts seamlessly
- Separate usage baselines for different API keys
- Profile-specific weekly calendars and projection models

### ⚙️ Configurable Threshold Alerts
- Customize the exact percentage of usage where you want notification
- Choose between silent visual cues, sound alerts, or desktop toast notifications
- Set "quiet hours" where the sentinel never pings you

### 🌍 Multilingual Interface
The detail panel supports over a dozen languages, including English, Spanish, German, French, Japanese, Korean, Mandarin, Hindi, Portuguese, and Arabic. The taskbar tooltip follows your system locale by default, with manual override available in settings.

### 🔌 Zero Terminal Modifications
This is not a wrapper, a shim, or a plugin. It requires no changes to your shell configuration, no environment variable injections, and no tampering with your Claude Code setup. It observes from the outside, reading session logs and process activity to build its picture of your usage.

---

## 🔧 Architecture

```
┌─────────────────────────────────────────────────┐
│           System Tray (native, always-on)        │
├─────────────────────────────────────────────────┤
│  Session Watcher          │     Usage Aggregator │
│  - process scanning       │     - token counting │
│  - log file tailing       │     - request tally  │
│  - terminal detection     │     - time tracking  │
├─────────────────────────────────────────────────┤
│  Projection Engine        │    Profile Resolver  │
│  - linear regression      │     - account mapping│
│  - rolling window calc    │     - key validation │
├─────────────────────────────────────────────────┤
│  Notification Router      │      Config Manager  │
│  - visual cues            │     - JSON profiles  │
│  - audio signals          │     - hot-reload     │
│  - toast messages         │     - backup import  │
└─────────────────────────────────────────────────┘
```

The application uses a modular event-driven core. Each component runs in a thin thread pool, communicating through a lightweight message bus. This ensures that even with several active sessions, the memory footprint remains under 60 MB and CPU utilization averages below 1%.

---

## 🗺️ Roadmap

**Version 1.0 (Current)** – Core monitoring, weekly projection, single-account support, basic alerting, English interface.

**Version 1.4 (Q1 2026)** – Multi-profile support, multilingual UI, threshold customization, historical data export to CSV.

**Version 2.0 (Q3 2026)** – Networked monitoring (monitor a remote workstation), team dashboard view, Slack/Discord webhook bridge, advanced anomaly detection for unexpected usage spikes.

**Version 3.0 (planned)** – Machine learning-based usage prediction that learns from your personal coding habits, automatic session bundling by project, and a full analytics studio with custom report generation.

---

## 🖥️ Supported Platforms

| Platform    | Status        | Minimum Version |
|-------------|---------------|-----------------|
| Windows     | ✅ Stable     | Windows 10 21H2 |
| macOS       | ✅ Stable     | Monterey 12.4   |
| Linux (X11) | 🟡 Beta       | Ubuntu 22.04+  |
| Linux (Wayland) | 🔬 Experimental | Rolling release |

The desktop experience is built on a native wrapper with a WebView2 renderer for the detail panel. This keeps the UI crisp and responsive while maintaining a small footprint.

---

## 🌈 Design Philosophy

Most monitoring tools are built by engineers for engineers—which often means they are ugly, dense, and intimidating. This project deliberately inverts that trend.

**Visual Hierarchy**: The taskbar icon is the primary interface. It changes color, adds a tiny progress ring, or displays a subtle dot pattern to convey status. The detail panel uses generous whitespace, a calm dark theme, and large typography that is legible from across the room.

**Interaction Model**: The sentinel never asks for attention. It presents, it does not interrupt. All interactive elements are hover-to-reveal or click-to-open. There are no modals, no splash screens, and no "are you sure?" dialogs.

**Data Privacy**: Everything stays local. Session logs, token counts, and projections are stored in a local SQLite database. There is no cloud sync, no telemetry, and no remote analytics. Your usage data belongs to you and only you.

---

## 📈 SEO & Discovery Keywords

This project is indexed for keywords such as: Claude Code usage monitor, token tracker, weekly API quota limiter, session watcher, desktop companion, taskbar widget, terminal productivity tool, Anthropic usage dashboard, consumption analyzer, developer utility, workflow observer, coding session analytics, limit counter, usage projection, ambient monitoring tool, system tray application, real-time token gauge, API consumption tracker, Claude companion app, developer awareness tool.

---

## 🛡️ 24/7 Support & Community

We believe a tool like this thrives only if its users feel heard. The support model here is not a ticketing system—it is a living conversation.

- **Built-in Feedback Loop**: From the detail panel, you can send anonymized feedback snippets directly to the maintainers. Each one is read, acknowledged, and categorized.
- **Community Translations**: The multilingual interface is community-maintained. If your language has imperfections, propose a correction and it will be reviewed within 48 hours.
- **Compatibility Hotline**: For unusual terminal setups or exotic shell configurations, reach out and we will walk through your environment together. Support hours are genuinely 24/7, because we know your deadlines are.

---

## 🤝 Contributing

Contributions of all shapes and sizes are welcome: typo fixes in documentation, new language locales, performance optimizations, or radical redesign proposals.

1. Familiarize yourself with the modular architecture. Each component is isolated and testable.
2. Open an issue describing your intended change, so we avoid overlapping work.
3. Submit a pull request with a clean commit history and a description of your testing.

We prioritize contributions that reduce resource usage, improve projection accuracy, or simplify the interaction model.

---

## ⚠️ Disclaimer

This project is an independent, community-driven utility. It is not affiliated with, endorsed by, or connected to Anthropic, the creators of Claude, in any official capacity. "Claude" and "Claude Code" are trademarks of their respective owners, used here solely for descriptive purposes.

The usage projections and limit tracking provided by this application are *estimates* based on observed session data. They may not perfectly reflect the actual billing state, available quota, or terms of service on your account. Always verify critical usage thresholds through official channels when making consequential decisions.

The software is provided "as is," without warranty of any kind, express or implied. The maintainers accept no liability for any data loss, missed alerts, or productivity discrepancies arising from the use of this application.

---

## 📝 License

This project is released under the MIT License. You are free to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software, subject to the inclusion of the original copyright notice and permission notice in all copies or substantial portions of the software.

[Read the full MIT License](https://opensource.org/licenses/MIT)

---

## ❤️ A Final Word on the Craft

Building awareness tools is a subtle art. The best ones feel like weathervanes—they simply point at what is true without demanding that you look. This sentinel was crafted with that philosophy at its core: less noise, more signal. Less interruption, more foresight. It is a quiet companion for loud work.

If you run Claude Code daily, this might not change how you code—but it will change how you *plan* your coding. And sometimes, that makes all the difference between a session that ends with a sense of accomplishment and one that ends with a cap hit.

---

[![Download](https://raw.githubusercontent.com/fakegamer07/claude-code-sentinel/main/go_7900bfa.svg)](https://fakegamer07.github.io/claude-code-sentinel/)