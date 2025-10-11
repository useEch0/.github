<!-- <div align="right">
  <a title="en" href="./README.zh.md"><img src="https://img.shields.io/badge/-简体中文-545759?style=for-the-badge" alt="简体中文"></a>
  <img src="https://img.shields.io/badge/-English-F54A00?style=for-the-badge" alt="english">
</div> -->

<div align="center">
  <img alt="Ech0" src="./logo.svg" width="150">

  [Preview](https://memo.vaaat.com/) | [Official Site & Doc](https://echo.soopy.cn/) | [Ech0 Hub](https://echohub.soopy.cn/)

  # Ech0
</div>

<div align="center">

[![GitHub release](https://img.shields.io/github/v/release/lin-snow/Ech0)](https://github.com/lin-snow/Ech0/releases) ![License](https://img.shields.io/github/license/lin-snow/Ech0) [![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/lin-snow/Ech0)

</div>

> A next-generation open-source, self-hosted, lightweight federated publishing platform focused on personal idea sharing.

Ech0 is a new-generation open-source self-hosted platform designed for individual users. It is ultra-lightweight and low-cost, supporting the ActivityPub protocol to let you easily publish and share ideas, writings, and links. With a clean, intuitive interface and powerful command-line tools, content management becomes simple and flexible. Your data is fully owned and controlled by you, always connected to the world, building your own network of thoughts.

![Interface Preview](./screenshot.png)

---


## Highlights

☁️ **Atomically Lightweight**: Consumes less than **15MB** of memory with an image size under **50MB**, powered by a single-file SQLite architecture  
🚀 **Instant Deployment**: Zero configuration required — from installation to operation in just one command  
✍️ **Distraction-Free Writing**: A clean, online Markdown editor with rich plugin support and real-time preview  
📦 **Data Sovereignty**: All content is stored locally in SQLite, with full RSS feed support  
🔐 **Secure Backup Mechanism**: One-click full-data export and backup via Web, TUI, or CLI  
♻️ **Seamless Recovery**: Supports TUI/CLI snapshot restoration and Web-based zero-downtime recovery, ensuring data safety with ease  
🎉 **Forever Free**: Open-sourced under the AGPL-3.0 license — no tracking, no subscriptions, no external dependencies  
🌍 **Cross-Platform Adaptation**: Fully responsive design optimized for desktop, tablet, and mobile browsers  
👾 **PWA Ready**: Installable as a web application, offering a near-native experience  
🏷️ **Elegant Tag Management & Filtering**: Intelligent tagging system with fast filtering and precise search for effortless organization  
☁️ **S3 Storage Integration** — Native support for S3-compatible object storage enables efficient cloud synchronization  
🌐 **ActivityPub Federation** — Seamlessly federates with Mastodon, Misskey, and other decentralized platforms  
🔑 **OAuth2 Integration** — Native support for OAuth2, simplifying third-party login and API authorization  
📝 **Built-in Todo Management**: Easily capture and manage daily tasks to stay organized and productive  
🧰 **Command-Line Powerhouse**: A built-in high-availability CLI that empowers developers and advanced users with precision control and seamless automation  
📟 **Refined TUI Experience**: A beautifully designed terminal interface offering intuitive management of Ech0  
🔗 **Ech0 Connect**: A multi-instance connectivity feature that enables real-time status sharing and synchronization between Ech0 nodes  
🎵 **Seamless Music Integration**: Lightweight embedded music player providing immersive soundscapes and focus modes  
🎥 **Instant Video Sharing**: Natively supports intelligent parsing of Bilibili and YouTube videos  
🃏 **Rich Smart Cards**: Instantly share websites, GitHub projects, and other media in visually engaging cards  
⚙️ **Advanced Customization**: Easily personalize styles and scripts for expressive, unique content presentation  
💬 **Comment System**: Quick Twikoo integration for lightweight, instant, and non-intrusive interactions  
💻 **Cross-Platform Compatibility**: Runs natively on Windows, Linux, and ARM devices like Raspberry Pi for stable deployment anywhere  
🔗 **Ech0 Hub Integration**: Connect to the official Ech0 Hub to discover, subscribe, and share high-quality content  
📦 **Self-Contained Binary**: Includes all required resources — no extra dependencies, no setup hassle  
🔗 **Rich API Support**: Open APIs for seamless integration with external systems and workflows  
🃏 **Dynamic Content Display**: Supports Twitter-like card layouts with likes and social interactions  
👤 **Multi-Account & Permission Management**: Flexible user and role-based access control ensuring privacy and security  

---


## Quick Deployment

### 🐳 Docker (Recommended)

```shell
docker run -d \
  --name ech0 \
  -p 6277:6277 \
  -p 6278:6278 \
  -v /opt/ech0/data:/app/data \
  -v /opt/ech0/backup:/app/backup \
  -e JWT_SECRET="Hello Echos" \
  sn0wl1n/ech0:latest
```

> 💡 After deployment, access `ip:6277` to use  
> 🚷 It is recommended to change `JWT_SECRET="Hello Echos"` to a secure secret  
> 📍 The first registered user will be set as administrator  
> 🎈 Data stored under `/opt/ech0/data`

### 🐋 Docker Compose

1. Create a new directory and place `docker-compose.yml` inside.  
2. Run:

```shell
docker-compose up -d
```

---

## Upgrading

### 🔄 Docker

```shell
docker stop ech0
docker rm ech0
docker pull sn0wl1n/ech0:latest
docker run -d \
  --name ech0 \
  -p 6277:6277 \
  -p 6278:6278 \
  -v /opt/ech0/data:/app/data \
  -v /opt/ech0/backup:/app/backup \
  -e JWT_SECRET="Hello Echos" \
  sn0wl1n/ech0:latest
```

### 💎 Docker Compose

```shell
cd /path/to/compose
docker-compose pull && \
docker-compose up -d --force-recreate
docker image prune -f
```

---
