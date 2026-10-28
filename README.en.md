# FastDown · All-in-one Download Manager for Windows

> **A free alternative to IDM**: direct links with multi-threaded acceleration, magnet / BitTorrent,
> video & audio extraction, and subtitles — all in one client.
> Bundles **yt-dlp / ffmpeg / aria2c**, so there is nothing to install or configure.

![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078D4)
![Type](https://img.shields.io/badge/type-download%20manager-2E7D32)
![IDM](https://img.shields.io/badge/IDM-alternative-C62828)
![Price](https://img.shields.io/badge/price-free-success)

[简体中文](README.md) | **English**

> This repository only hosts **release builds, the video tutorial and documentation**. No source code.

---

## ✨ Four jobs, one app

| What you need | How FastDown does it |
|---|---|
| Ordinary files (zip / exe / iso / pdf…) | Paste the direct link — **multi-threaded chunking + resume** |
| Magnet links / `.torrent` files | Built-in BitTorrent engine, always on; pick files from a list before downloading |
| Video, audio and subtitles on web pages | One-click sniffing via the floating bar — **4K down to 480P**, audio-only MP3, multi-select subtitles |
| Whole pages, channels, playlists | Bilibili collections, YouTube playlists, profile pages — select and queue them all at once |

## 🚀 Highlights

- **Floating bar sniffing** — a “⬇ 快下” button appears on video pages, follows the current video and lists real filename + resolution + size
- **Page resource panel** — images / video / audio / subtitles / lyrics / documents / magnet links, filterable by size, resolution and format
- **Browser takeover** — click a magnet link, a `.torrent` or a direct file link and FastDown picks it up, no copy-paste
- **Quality & audio tracks** — 4K to 480P, audio-only MP3, automatic AAC selection so you never get “video without sound”
- **Subtitle export** — multi-select subtitles, plus optional `.lrc` lyric export
- **Automatic proxy** — overseas sites are detected and routed through your system proxy, domestic sites stay direct
- **Persistent queue** — tasks survive restarts; right-click to retry or open the containing folder
- **Localized UI** — Simplified Chinese / Traditional Chinese / English, five built-in themes

## 🌐 Supported sites (mainstream)

- **China**: Bilibili, Douyin, Kuaishou, Weibo, Xiaohongshu, Xigua, Tencent Video, Youku, iQIYI, AcFun, Mango TV
- **Global**: YouTube, X (Twitter), TikTok, Instagram, Facebook, Vimeo, Dailymotion, Twitch
- **Music**: NetEase Music, QQ Music, Kugou, Kuwo
- **Other**: magnet / BitTorrent links, `.torrent` files, mp4 / m3u8 streams, any direct file link, CCTV programme pages

> For the rare site that cannot be parsed automatically, use the floating bar or the page resource panel instead.

## ⬇️ Download

Grab the latest build from [**Releases**](../../releases/latest):

| File | Description |
|---|---|
| `FastDown_v6.1_Setup_win64.zip` | Installer (setup wizard + client + browser extension + manual) |
| `FastDown_v6.1_Tutorial_zh.mp4` | 6-minute video tutorial (Chinese narration, subtitles included) |

Unzip and run `FastDown_Setup.exe`. **Keep the `FastDown` folder next to `FastDown_Setup.exe`** — the installer copies files from it.

**Requirements**: Windows 10 / 11 (64-bit). No admin rights needed unless you install into `Program Files`.

## 🎬 Video tutorial (6 min)

[![Click the cover to watch](https://i2.hdslb.com/bfs/archive/fed70cd3600d03e611ded26ae179c3d059a77041.jpg@1280w.jpg)](https://www.bilibili.com/video/BV16qn96uEDi)

▶ **Click the cover to play** (Bilibili, 6 minutes, Chinese subtitles)

- Offline copy: [`FastDown_v6.1_Tutorial_zh.mp4`](https://github.com/shiyi8686/FastDown/releases/download/v6.1/FastDown_v6.1_Tutorial_zh.mp4) (259 MB)
- Subtitles: [Chinese](https://github.com/shiyi8686/FastDown/releases/download/v6.1/FastDown_v6.1_Tutorial_zh.srt) · [English](https://github.com/shiyi8686/FastDown/releases/download/v6.1/FastDown_v6.1_Tutorial_en.srt)

> The UI is currently Chinese-only (an English option is on the roadmap). English subtitles are provided for the tutorial.

## 🔧 Install

1. Unzip and run `FastDown_Setup.exe`
2. Choose a location → Next → Finish
3. Launch **快下FastDown** — the client listens on `127.0.0.1:18586` for the browser extension
4. Install the browser extension (**pick exactly one**):

   | Browser | Steps |
   |---|---|
   | Chrome | `chrome://extensions` → enable Developer mode → “Load unpacked” → select `浏览器扩展\Chrome(谷歌浏览器)` |
   | Edge | `edge://extensions` → enable Developer mode → “Load unpacked” → select `浏览器扩展\Edge(微软浏览器)` |
5. Open any video page — the “⬇ 快下” floating bar means it works

> Chrome 137+ disables self-installed `.crx` files by default; “Load unpacked” is the reliable path.

## 📖 How to use

1. **Paste a link (most common)** — copy a video or file URL, paste it into the top input box, click “添加任务” (Add task), choose quality
2. **Floating bar** — click “⬇ 快下” on a video page, pick the resolution, download
3. **Page resource panel** — click the extension icon, tick the resources you want from the whole page
4. **Magnet / BitTorrent** — paste a `magnet:` link, or click “🧲 打开种子” (Open torrent) to load a local `.torrent`
5. **Batch** — Bilibili collections, YouTube playlists / channels, profiles: paste and tick from the list

## ❓ FAQ

**“Cannot reach the client” in the floating bar**
Start the FastDown desktop client first (it owns `127.0.0.1:18586`). If it is already running, close and reopen it.

**Download does not start / stuck at 0%**
Usually a link that requires login or has expired. Import browser cookies in Settings, or re-copy a fresh link.

**YouTube / TikTok slow or failing**
The client proxies these automatically — make sure your proxy app is running and not on a datacenter node.

**Video/audio list in the panel is empty**
Those resources load progressively: play the video for a few seconds, then click the extension icon.

**Does a direct `.zip` / `.exe` link trigger a quality picker?**
No. Ordinary file links are downloaded as-is instead of being sent to the video parser.

## 🆕 Changelog

### v6.1 (2026-10-28)
- Fix: Chrome extension error `background.scripts requires manifest version of 2 or lower` (per-browser manifests)
- Fix: content script blocked by page CSP when calling `127.0.0.1` on Chrome (requests now proxied through the service worker)
- Fix: relative download links (e.g. GitHub Releases assets) failing with `unknown url type`
- Fix: Bilibili “unsupported link format” (URL canonicalization + automatic retry)
- Improvement: show the parsed URL when parsing fails

## 🔒 Verify

Every release asset ships with a `sha256` file:

```powershell
Get-FileHash .\FastDown_v6.1_Setup_win64.zip -Algorithm SHA256
```

## ⚠️ Disclaimer

This tool is provided for personal study and research. Do not use it to infringe copyright or violate a site's terms of service. All downloaded content remains the property of its respective owners.
