# 🥧 ChetuPiHomelab

My personal Raspberry Pi homelab, built to learn Linux, Docker, networking, self-hosting, and server administration.

## 🖥️ Hardware

- Raspberry Pi
- SSD storage
- Debian / Raspberry Pi OS
- Docker

## 🐳 Services

| Service | Purpose |
|---|---|
| ☁️ Nextcloud | Self-hosted cloud storage |
| 🗄️ MariaDB | Nextcloud database |
| ⚡ Redis | Nextcloud caching |
| 🐳 Portainer | Docker management |
| 📊 Uptime Kuma | Service monitoring |
| 🏠 Heimdall | Homelab dashboard |
| 🔐 Tailscale | Private remote access |

## ☁️ Nextcloud

The main service running on the Pi.

- Nextcloud 34
- MariaDB 11.8
- Redis 7 Alpine
- FFmpeg-enabled Nextcloud image
- Docker Compose
- Cron background jobs
- PHP OPcache JIT disabled

### Architecture

```text
                    ┌─────────────────┐
                    │    Nextcloud    │
                    │  Apache + PHP   │
                    └────────┬────────┘
                             │
                 ┌───────────┴───────────┐
                 │                       │
          ┌──────▼──────┐        ┌──────▼──────┐
          │   MariaDB   │        │    Redis    │
          │   Database  │        │    Cache    │
          └─────────────┘        └─────────────┘
