# Personal Homelab

A personal Raspberry Pi homelab built as a practical environment for learning Linux system administration, containerization, networking, self-hosting, and server maintenance.

The project began with a Raspberry Pi and SSD and gradually developed into a small self-hosted infrastructure running several services through Docker. The goal was not simply to deploy applications, but to understand how the individual components fit together, how they communicate, and how to maintain the system reliably over time.

## Overview

The server was designed primarily for private use within a home network, with remote access provided through Tailscale rather than exposing services directly to the public internet.

Docker is used as the primary application platform, with Portainer providing a graphical interface for managing containers and stacks.

The main services deployed as part of the project were:

| Service | Role |
|---|---|
| Nextcloud | Self-hosted file storage and synchronization |
| MariaDB | Database backend for Nextcloud |
| Redis | Caching and supporting Nextcloud performance |
| Portainer | Docker and container management |
| Uptime Kuma | Service availability monitoring |
| Heimdall | Web dashboard for self-hosted services |
| Tailscale | Private remote access |

## Architecture

The general architecture of the system was:

```text
                         Home Network
                              |
                              |
                     +--------+--------+
                     |  Raspberry Pi   |
                     |                 |
                     |     Docker      |
                     +--------+--------+
                              |
          +-------------------+-------------------+
          |                   |                   |
     +----+-----+       +-----+-----+       +-----+------+
     | Nextcloud|       | Portainer |       | Uptime     |
     |          |       |           |       | Kuma       |
     +----+-----+       +-----------+       +------------+
          |
      +---+----------------+
      |                    |
+-----+------+       +-----+------+
|  MariaDB   |       |   Redis    |
|  Database  |       |   Cache    |
+------------+       +------------+

                         Tailscale
                             |
                             |
                    Remote private access
