# Pterodactyl Web Eggs

A collection of Pterodactyl eggs for running web applications.

## Available Eggs

| Egg | Description | Stack |
|-----|-------------|-------|
| [pterodactyl-nginx-egg](https://github.com/Ym0T/pterodactyl-nginx-egg) | Full-featured PHP web server | Nginx + PHP 8.x |
| [pterodactyl-rust-web-egg](https://github.com/Ym0T/pterodactyl-rust-web-egg) | Rust web applications | Rust Toolchain |

---

## Pterodactyl Nginx Egg

A versatile egg featuring Nginx, PHP 8.x, WordPress, Git, Composer, Cronjob, ionCube Loader, Auto-Update, and Cloudflare Tunnel support.

### Features

- **PHP Versions**: 8.2, 8.3, 8.4, 8.5
- **WordPress**: Optional WordPress installation
- **Composer**: Auto-install PHP dependencies
- **Git Module**: Auto `git pull` on restart
- **Cronjob**: Container-native cron engine
- **ionCube Loader**: Auto-detected for encrypted PHP
- **Certbot**: SSL certificates via DNS-01 challenge
- **Cloudflare Tunnel**: Secure tunnel support
- **Auto-Update**: Differential updates via Tavuru API
- **Multi-arch**: AMD64 & ARM64

### What Gets Updated

| Updated | Not Updated |
|---------|-------------|
| modules/ | www/ (user content) |
| nginx/ | uploads |
| php/ | databases |
| start-modules.sh | |

---

## Pterodactyl Rust Web Egg

An egg for running Rust web applications with pre-installed Rust toolchain.

### Features

- **Rust Toolchain**: cargo, clippy, rustfmt pre-installed
- **Docker Images**: Stable & Nightly variants
- **Log Cleaner**: Auto cleanup of old logs
- **Cloudflare Tunnel**: Secure tunnel support
- **Auto-Update**: Differential updates via Tavuru API

### Docker Images

| Image | Use Case |
|-------|----------|
| `ghcr.io/ym0t/pterodactyl-rust-web-egg:stable` | Production (recommended) |
| `ghcr.io/ym0t/pterodactyl-rust-web-egg:nightly` | Experimental features |

### What Gets Updated

| Updated | Not Updated |
|---------|-------------|
| modules/ | app/, src/ |
| start-modules.sh | Cargo.toml |
| | data/, logs/ |

---

## Common Features

Both eggs share these capabilities:

- **Auto-Update System**: Smart differential updates that only download changed files
- **Cloudflare Tunnel**: Expose your server without port forwarding
- **Log Management**: Automatic cleanup of old logs and temp files
- **User Data Protection**: Updates never touch user content or application data

### Auto-Update Configuration

| Variable | Default | Description |
|----------|---------|-------------|
| `AUTOUPDATE_STATUS` | `1` | Enable update checking |
| `AUTOUPDATE_FORCE` | `1` | Apply updates automatically |

---

## License

- Nginx Egg: [MIT License](https://choosealicense.com/licenses/mit/)
- Rust Egg: [GPL-3.0 License](https://choosealicense.com/licenses/gpl-3.0/)
