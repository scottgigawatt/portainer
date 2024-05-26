# Portainer for Synology

This repository contains a Docker Compose configuration tailored for Synology NAS environments, simplifying the setup process for managing Docker containers by integrating Portainer.

## Overview

The `docker-compose.yml` file in this repository configures a Portainer container to provide an easy-to-use web interface for managing Docker containers on a Synology NAS.

## Included Tool

- **Portainer**: Manages Docker containers through a user-friendly web interface. [More info](https://www.portainer.io/)

## Docker Compose Configuration

Ensure your Docker Compose version is compatible with version 2.9.

### Services Configuration

#### Portainer

- **Image**: `portainer/portainer-ce:${PORTAINER_TAG}`
- **Pull Policy**: Always
- **Container Name**: `portainer-${PORTAINER_TAG}`
- **Restart Policy**: Unless stopped
- **Network Mode**: Host
- **Hostname**: portainer

#### Ports

- **8010:8000**
- **9443:9443**

#### Volumes

- `${HOST_DOCKER_PATH}/portainer/data:/data:rw`
- `/var/run/docker.sock:/var/run/docker.sock`
- `/etc/localtime:/etc/localtime:ro`

## Usage

### Starting the Service

Follow these steps to start the Portainer service:

1. Clone this repository to your Synology NAS.
2. Navigate to the directory containing the `docker-compose.yml` file.
3. Open a terminal or SSH into your Synology NAS.
4. Run `docker-compose up -d` to start the container in detached mode.
5. Access the Portainer web interface at `https://<your-nas-ip>:9443`.

### Managing Docker Config Environment Variables

Manage Docker configuration environment variables in the `.env` file. Override these variables easily on the command line when starting the Docker Compose stack:

```bash
PORTAINER_TAG="latest" docker-compose up -d
```

Adjust the values of these environment variables to your requirements.

### Secure Access to Synology Applications

Use DSM 7 Reverse Proxy to configure secure access to Synology applications. Follow the guide [here](https://mariushosting.com/synology-how-to-use-reverse-proxy-on-dsm-7/) for DSM 7.

> **Note**: If you encounter "Socket closed" errors when accessing the DSM UI via reverse proxy and trying to open terminals for running containers, enable WebSocket for the reverse proxy record:
>
> 1. Go to `Control Panel -> Application Portal -> Reverse Proxy`.
> 2. Select `Edit` for your reverse proxy record.
> 3. Navigate to the `Custom Header` tab.
> 4. From the `Create` dropdown, select `WebSocket`.
> 5. Save the changes to resolve the issue.

## Environment Details

Tested on Synology DS916+ running DSM 7.2.1-69057 Update 5, with Docker Compose version v2.9.0-6413-g38f6acd.

## License

Licensed under the Apache 2 License - see [LICENSE](LICENSE) for details.

---

Contribute or provide feedback to improve this repository. Happy container management with Portainer!
