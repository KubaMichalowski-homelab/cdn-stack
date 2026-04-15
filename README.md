# cdn-stack

This repository contains the configuration for my CDN deployment.

## Environment Setup
The stack relies on the following environment variables:

| Variable | Description | Example |
| :--- | :--- | :--- |
| `TUNNEL_TOKEN` | Cloudflare Tunnel token | (`Secret`) |

## Persistent Storage
I use bind mounts for data persistence. Ensure these paths exist on the Docker host:
* `/opt/docker/cdn/uploads:/data:ro` - CDN uploads
* `./nginx/default.conf:/etc/nginx/conf.d/default.conf` - Nginx configuration
* `./nginx/00-global.conf:/etc/nginx/conf.d/00-global.conf:ro` - Global nginx configuration override

---

[Back to Homelab Overview](https://github.com/KubaMichalowski-homelab)
