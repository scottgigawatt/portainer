<hr />

<p align="center">
  <em>⚓ Star this repo to chart your course to smoother container management.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/github/license/scottgigawatt/portainer?label=Charter%20License" alt="License" />
  <img src="https://img.shields.io/github/last-commit/scottgigawatt/portainer?label=Last%20Docking&logo=git" alt="Last Commit" />
  <img src="https://img.shields.io/github/repo-size/scottgigawatt/portainer?label=Storage%20Crate" alt="Repo Size" />
</p>

<hr />

# 🚢 Portainer for Synology

## ⚓ Dock Overview

This repository provides a streamlined Docker Compose setup for deploying Portainer on Synology NAS, giving you helm control over your Docker containers with a clean and intuitive web interface.

Explore the full configuration in [`docker-compose.yml`](docker-compose.yml).

## 🧰 Equipment Manifest

- **Portainer**: A web UI to manage Docker containers with ease. [More info](https://www.portainer.io/)

## 📦 Deployment Orders

### ⚙️ Launch Sequence

1. SSH into your Synology NAS.
2. Clone this repository.
3. Copy the [`example.env`](example.env) file to `.env` and adjust it to your environment.
4. Run the deployment:

   ```bash
   docker-compose up -d
   ```

5. Access Portainer at `https://<your-nas-ip>:9443`.

### 🪝 Environmental Tuning

All Docker config values are managed via the `.env` file. You can override any of them on-the-fly:

```bash
PORTAINER_TAG="2.31.0" docker-compose up -d
```

Tweak values to meet your deployment needs.

## 🛡️ Fortifying the Harbor Gate

To enable secure access, use Synology DSM 7’s built-in reverse proxy. Follow this [guide](https://mariushosting.com/synology-how-to-use-reverse-proxy-on-dsm-7/).

> [!WARNING]
> 🧱 If you see “Socket closed” errors when using a reverse proxy to access container terminals, enable WebSocket:
>
> 1. DSM → Control Panel → Application Portal → Reverse Proxy
> 2. Edit your rule → go to the `Custom Header` tab
> 3. Use `Create > WebSocket`
> 4. Save and you're good to sail

## 🧭 System Charting

Tested on:

- Synology DS1522+ and DS916+
- DSM 7.2.2
- Docker Compose v2.9

> [!NOTE]
> 🛟 This setup should work on other platforms too—any port that runs Docker Compose can join the fleet.

## 📜 Charter Agreement

Licensed under the Apache 2 License. See [LICENSE](LICENSE) for full terms.

---

```
     __/___
 _____/______|
 \              \
  ~~~~~~\~~~~~~~
         \
  ⚓ Portainer Harbor Control
```

Contribute or raise a flag with feedback. Steady sailing! 🌊
