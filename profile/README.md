<!-- <div align="right">
  <a title="en" href="./README.zh.md"><img src="https://img.shields.io/badge/-简体中文-545759?style=for-the-badge" alt="简体中文"></a>
  <img src="https://img.shields.io/badge/-English-F54A00?style=for-the-badge" alt="english">
</div> -->

<div align="center">
  <img alt="Ech0" src="./logo.svg" width="150">

  [Preview](https://memo.vaaat.com/) | [Official Site](https://echo.soopy.cn/) | [Documentation](https://echodoc.soopy.cn/) | [Ech0 Hub](https://echohub.soopy.cn/)

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

- ☁️ **Ultra Lightweight** — Memory usage under **15MB**, image size under **50MB**, single SQLite file storage.
- 🚀 **Blazing Fast Deployment** — No configuration needed, install and use with just one command.
- 🧰 **Command-line Power** — Built-in high-availability CLI tools that support one-click backup, restore, and export.
- 📟 **TUI Friendly** — Terminal-friendly interactive interface to manage Ech0 from the TUI.
- ✍️ **Distraction-Free Writing** — Clean online Markdown editor with rich plugin support and live preview.
- 📦 **Data Ownership** — All content stored locally in SQLite, with RSS feed support.
- 🔐 **Secure Backup** — One-click export/backup/import via Web, TUI, or CLI.
- ♻️ **Seamless Restore** — Restore any backup via TUI or CLI to ensure data safety.
- 🎉 **Completely Free** — Open-source under AGPL-3.0 with no tracking, subscription, or dependency.
- 🌍 **Cross-Device Compatible** — Fully responsive on desktop, tablet, and mobile.
- 👾 **PWA Support** — Can be installed as a Web App.
- ☁️ **S3 Storage Support** — Native integration with S3-compatible object storage for local or cloud backups.
- 🌐 **ActivityPub Federation** — Native ActivityPub support for interoperability with Mastodon, Misskey etc.
- 📝 **Built-in Todo Management** — Record and track daily tasks efficiently.
- 🔑 **OAuth2 Integration** — Full OAuth2 support for secure third-party authentication and API access.
- 🔗 **Ech0 Connect** — Cross-instance content aggregation, subscription, and synchronization.
- 🎵 **Music Integration** — Lightweight audio player for local streaming and immersive background music.
- 🎥 **Video Sharing** — Native support for Bilibili/YouTube smart parsing.
- 🃏 **Rich Card Support** — Share website links, GitHub projects, and other media-rich content.
- ⚙️ **Advanced Customization** — Custom styles and scripts for enhanced content presentation.
- 💬 **Comment System** — Integrate Twikoo for lightweight interaction and feedback.
- 💻 **Cross-Platform** — Native support for Windows, Linux, and ARM devices like Raspberry Pi.
- 🔗 **Official Ech0 Hub Integration** — Submit content to the Ech0 Hub ecosystem easily.
- 🌐 **Self-Hosted Ech0 Hub** — Use your Connect list as a content source.
- 📦 **Self-contained Binary** — Full frontend resources included, single binary file ready to run.
- 🔗 **Rich API Support** — Open API available for integration with other systems.
- 🃏 **Content Display** — Supports X (Twitter)-style card display with social interactions.
- 👤 **Multi-user and Permissions** — Flexible account and permission management for secure access.

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