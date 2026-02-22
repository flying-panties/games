# 🎬 @denzy-official/youtube_scraper v2.0.0

<p align="center">
  <img src="https://img.shields.io/npm/v/@denzy-official/youtube_scraper?color=red&style=for-the-badge">
  <img src="https://img.shields.io/npm/dt/@denzy-official/youtube_scraper?color=blue&style=for-the-badge">
  <img src="https://img.shields.io/badge/Node.js-14+-green?style=for-the-badge">
</p>

Lightweight YouTube search & downloader toolkit for Node.js 🚀  
Fast. Clean. No API key required.

---

# ✨ Features

- 🔎 Search YouTube videos
- 🎵 Download MP3
- 🎥 Download MP4 (auto highest quality)
- 🧠 Auto resolve from:
  - YouTube URL
  - Video ID
  - Search query
- 📦 Clean JSON output
- 🛡️ No API key needed

---

# 🚀 Installation

```bash
npm install @denzy-official/youtube_scraper
```

---

# ⚡ Quick Start

```js
const yt = require('@denzy-official/youtube_scraper')

// MP3
const mp3 = await yt.ytmp3('bersenja gurau')
console.log(mp3)

// MP4
const mp4 = await yt.ytmp4('https://youtu.be/jmvX6XyvCy0')
console.log(mp4)

// Search
const search = await yt.search('lofi hip hop')
console.log(search)
```

---

# 📚 API Reference

---

## 🎵 `.ytmp3(input)`

Download YouTube audio as MP3.

```js
const result = await yt.ytmp3('https://youtu.be/jmvX6XyvCy0')
```

### ✅ Example Response

```json
{
  "status": true,
  "creator": "@denzy-official/youtube_scraper",
  "metadata": {
    "title": "Hindia - Rumah ke Rumah",
    "url": "https://youtube.com/watch?v=jmvX6XyvCy0",
    "timestamp": "4:02",
    "views": 12345678,
    "author": {
      "name": "Hindia"
    }
  },
  "download": {
    "type": "mp3",
    "title": "Hindia - Rumah ke Rumah",
    "filesize": 6763939,
    "duration": 242,
    "url": "https://cdn.example.com/file.mp3",
    "filename": "Hindia - Rumah ke Rumah.mp3"
  }
}
```

---

## 🎥 `.ytmp4(input)`

Download YouTube video as MP4.

```js
const result = await yt.ytmp4('bersenja gurau')
```

### ✅ Example Response

```json
{
  "status": true,
  "creator": "@denzy-official/youtube_scraper",
  "metadata": {
    "title": "Hindia - Rumah ke Rumah",
    "url": "https://youtube.com/watch?v=jmvX6XyvCy0"
  },
  "download": {
    "type": "mp4",
    "title": "Hindia - Rumah ke Rumah",
    "quality": "720p",
    "url": "https://cdn.example.com/file.mp4",
    "filename": "Hindia - Rumah ke Rumah.mp4"
  }
}
```

---

## 🔎 `.search(query)`

Search YouTube videos.

```js
const result = await yt.search('lofi hip hop')
```

### ✅ Example Response

```json
{
  "status": true,
  "creator": "@denzy-official/youtube_scraper",
  "results": [
    {
      "title": "lofi hip hop radio",
      "url": "https://youtube.com/watch?v=xxxx",
      "duration": "LIVE",
      "views": 9876543,
      "author": "Lofi Girl",
      "thumbnail": "https://i.ytimg.com/vi/xxxx/hqdefault.jpg"
    }
  ]
}
```

---

# 📦 Full Example Usage

```js
const yt = require('@denzy-official/youtube_scraper')

async function main() {
  const mp3 = await yt.ytmp3('alan walker faded')
  console.log(mp3.download.url)

  const mp4 = await yt.ytmp4('https://youtu.be/60ItHLz5WEA')
  console.log(mp4.download.url)

  const search = await yt.search('anime opening')
  console.log(search.results[0])
}

main()
```

---

# 🛠 Requirements

- Node.js v14+
- Internet connection

---

# ⚠ Disclaimer

This module is intended for **educational purposes only**.  
Downloading copyrighted content without permission may violate YouTube's Terms of Service.

---

# ⭐ Support

If this project helps you:

⭐ Star this repository  
🔁 Share with other developers  

---

Made with ❤️ by **@denzy-official**
