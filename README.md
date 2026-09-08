# 🌸 温柔打卡日记

纯前端「打卡 + 心情日记」单页应用（数据保存在浏览器 localStorage），支持多主题切换，已启用 PWA（可添加到手机主屏、离线访问、全屏运行）。

## 项目文件

| 文件 | 说明 |
| --- | --- |
| `index.html` | 应用本体（单文件，含全部样式与逻辑） |
| `manifest.webmanifest` | PWA 安装清单（名称 / 图标 / standalone 全屏） |
| `sw.js` | Service Worker（离线缓存） |
| `icons/` | 应用图标（192/512/apple-touch 180/1024 主图） |

## 线上部署（Cloud Studio）

- 正式访问地址（HTTPS，不过期）：
  `https://75ca556928bd4570aa498460caeba8e0.codebuddy.cloudstudio.run`
- 说明：静态站点由 `serve` 托管在 Cloud Studio 云端沙箱（端口 8080）。`https` 正常，Service Worker / PWA 可用。
- 若一段时间未访问服务被休眠，重新部署即可恢复同一项目。

## 如何重新部署 / 更新

1. 修改 `index.html`、`manifest.webmanifest`、`sw.js` 或 `icons/` 后保存；
2. 使用 Cloud Studio 部署工具重新上传整个项目目录（`start: ["serve -l 8080"]`，端口 8080）。

> 注意：每次更新后若 `sw.js` 缓存版本（`CACHE` 变量）未变化，旧客户端可能仍使用缓存；改版时请同步递增 `sw.js` 顶部的 `CACHE` 版本号。

## 手机安装 PWA

1. 手机浏览器打开上面的线上地址（正式域名后无需 token）；
2. **iPhone/Safari**：分享按钮 → 「添加到主屏幕」；
3. **Android/Chrome**：右上菜单 → 「添加到主屏幕 / 安装应用」。
4. 安装后从主屏图标启动，应用将**全屏独立运行**，并支持离线打开。
