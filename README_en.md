# caddy-custom-build

Language: [中文](README.md) | **English**

[![Build Status](https://github.com/qichiyuhub/caddy-custom-build/actions/workflows/build-caddy.yml/badge.svg)](https://github.com/qichiyuhub/caddy-custom-build/actions)
[![Latest Release](https://img.shields.io/github/v/release/qichiyuhub/caddy-custom-build)](https://github.com/qichiyuhub/caddy-custom-build/releases/latest)
[![License](https://img.shields.io/github/license/qichiyuhub/caddy-custom-build)](LICENSE)

Pre-built Caddy binaries with 11 commonly used plugins, compiled via [xcaddy](https://github.com/caddyserver/xcaddy).  
Grab them from the [Releases](https://github.com/qichiyuhub/caddy-custom-build/releases/latest) page — available for `linux/amd64` and `linux/arm64`.

---

### Included Plugins

| # | Plugin | Purpose | Repository |
|---|--------|---------|------------|
| 1 | **Cloudflare DNS** | DNS-01 challenge for wildcard & internal certificates | [caddy-dns/cloudflare](https://github.com/caddy-dns/cloudflare) |
| 2 | **Aliyun DNS** | AliDNS challenge for automatic SSL issuance / renewal | [caddy-dns/alidns](https://github.com/caddy-dns/alidns) |
| 3 | **Tencent Cloud DNS** | DNSPod challenge for automatic SSL issuance / renewal | [caddy-dns/tencentcloud](https://github.com/caddy-dns/tencentcloud) |
| 4 | **Rate Limit** | HTTP request rate limiting | [mholt/caddy-ratelimit](https://github.com/mholt/caddy-ratelimit) |
| 5 | **Security** | Authentication & authorization (OAuth2 / OIDC / SAML / JWT) | [greenpau/caddy-security](https://github.com/greenpau/caddy-security) |
| 6 | **Layer 4** | TCP / UDP routing and Layer-4 reverse proxy | [mholt/caddy-l4](https://github.com/mholt/caddy-l4) |
| 7 | **Dynamic DNS** | Automatically updates public IP to DNS providers | [mholt/caddy-dynamicdns](https://github.com/mholt/caddy-dynamicdns) |
| 8 | **WebDAV** | WebDAV file sharing | [mholt/caddy-webdav](https://github.com/mholt/caddy-webdav) |
| 9 | **Cache Handler** | HTTP response caching | [caddyserver/cache-handler](https://github.com/caddyserver/cache-handler) |
| 10 | **GeoIP2** | IP geolocation via MaxMind GeoIP2 database | [zhangjiayin/caddy-geoip2](https://github.com/zhangjiayin/caddy-geoip2) |
| 11 | **Cloudflare IP Ranges** | Auto-syncs official Cloudflare IP ranges for `trusted_proxies` to resolve the real client IP | [WeidiDeng/caddy-cloudflare-ip](https://github.com/WeidiDeng/caddy-cloudflare-ip) |

See each plugin's repository for configuration details.

---

### How It Works

- GitHub Actions pulls the [latest Caddy release](https://github.com/caddyserver/caddy/releases/latest) on the 1st of each month and builds with xcaddy
- All 11 plugin modules are verified after build
- Builds are skipped if the Caddy version hasn't changed

---

### Usage

```bash
# Start Caddy
./caddy run --config /path/to/Caddyfile

# List integrated modules
./caddy list-modules
```

---

### Acknowledgements

- [Caddy](https://github.com/caddyserver/caddy)
- [xcaddy](https://github.com/caddyserver/xcaddy)
