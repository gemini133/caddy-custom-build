# caddy-custom-build

Language: **中文** | [English](README_en.md)

[![构建状态](https://github.com/qichiyuhub/caddy-custom-build/actions/workflows/build-caddy.yml/badge.svg)](https://github.com/qichiyuhub/caddy-custom-build/actions)
[![最新版本](https://img.shields.io/github/v/release/qichiyuhub/caddy-custom-build)](https://github.com/qichiyuhub/caddy-custom-build/releases/latest)
[![License](https://img.shields.io/github/license/qichiyuhub/caddy-custom-build)](LICENSE)

基于 [xcaddy](https://github.com/caddyserver/xcaddy) 自动构建的 Caddy，预装 11 个常用插件。  
直接从 [Releases](https://github.com/qichiyuhub/caddy-custom-build/releases/latest) 下载即可使用，提供 `linux/amd64` 和 `linux/arm64` 两个架构。

---

### 内置插件

| # | 插件 | 用途 | 仓库 |
|---|------|------|------|
| 1 | **Cloudflare DNS** | DNS-01 质询，自动签发泛域名 / 内网证书 | [caddy-dns/cloudflare](https://github.com/caddy-dns/cloudflare) |
| 2 | **阿里云 DNS** | AliDNS 质询，自动签发 / 续期证书 | [caddy-dns/alidns](https://github.com/caddy-dns/alidns) |
| 3 | **腾讯云 DNS** | DNSPod 质询，自动签发 / 续期证书 | [caddy-dns/tencentcloud](https://github.com/caddy-dns/tencentcloud) |
| 4 | **Rate Limit** | HTTP 请求限流 | [mholt/caddy-ratelimit](https://github.com/mholt/caddy-ratelimit) |
| 5 | **Security** | 身份验证与授权 (OAuth2 / OIDC / SAML / JWT) | [greenpau/caddy-security](https://github.com/greenpau/caddy-security) |
| 6 | **Layer 4** | TCP / UDP 协议分发与四层反向代理 | [mholt/caddy-l4](https://github.com/mholt/caddy-l4) |
| 7 | **Dynamic DNS** | 自动将本机公网 IP 更新到 DNS 服务商 | [mholt/caddy-dynamicdns](https://github.com/mholt/caddy-dynamicdns) |
| 8 | **WebDAV** | WebDAV 文件共享 | [mholt/caddy-webdav](https://github.com/mholt/caddy-webdav) |
| 9 | **Cache Handler** | HTTP 响应缓存 | [caddyserver/cache-handler](https://github.com/caddyserver/cache-handler) |
| 10 | **GeoIP2** | 基于 MaxMind 数据库的 IP 地理位置解析 | [zhangjiayin/caddy-geoip2](https://github.com/zhangjiayin/caddy-geoip2) |
| 11 | **Cloudflare IP Ranges** | 自动同步 Cloudflare 官方 IP 段，供 `trusted_proxies` 识别真实访客 IP | [WeidiDeng/caddy-cloudflare-ip](https://github.com/WeidiDeng/caddy-cloudflare-ip) |

各插件的配置方式请参考对应仓库文档。

---

### 构建机制

- 每月 1 号通过 GitHub Actions 自动拉取 [Caddy 最新 Release](https://github.com/caddyserver/caddy/releases/latest)，使用 xcaddy 编译
- 构建完成后自动校验全部 11 个插件模块的集成状态
- 若当月 Caddy 版本无更新，则跳过构建

---

### 使用

```bash
# 启动
./caddy run --config /path/to/Caddyfile

# 查看已集成的模块
./caddy list-modules
```

---

### 致谢

- [Caddy](https://github.com/caddyserver/caddy)
- [xcaddy](https://github.com/caddyserver/xcaddy)