🚀 PostPilot — Social Media Automation & Content Scheduler

> AI-powered social media scheduler with visual calendar, multi-platform posting, and AI content generation.

![License](https://img.shields.io/badge/license-MIT-blue) ![Vanilla JS](https://img.shields.io/badge/vanilla-JS-yellow) ![Platforms](https://img.shields.io/badge/platforms-5-brightgreen)

## 🚀 Quick Start
```bash
git clone https://github.com/YOUR_USERNAME/postpilot
open index.html
```

## ✨ Features
- **Multi-Platform Composer** — Post to Twitter/X, LinkedIn, Instagram, Facebook, YouTube
- **Visual Content Calendar** — Monthly grid with color-coded scheduled post chips
- **AI Content Writer** — Typewriter-effect generation, improve, shorten, hashtag suggest
- **Smart Scheduling** — Best-time suggestions based on engagement data
- **Queue Manager** — View, reorder, and delete upcoming posts
- **Hashtag Manager** — Tag pills with keyboard input

## 🔌 Real Scheduling Backend
```javascript
const schedule = require('node-schedule');

schedule.scheduleJob(post.datetime, async () => {
  await Promise.allSettled([
    post.platforms.includes('tw') && postToTwitter(post),
    post.platforms.includes('li') && postToLinkedIn(post),
    post.platforms.includes('ig') && postToInstagram(post),
  ]);
  await updatePostStatus(post.id, 'published');
});
```

## 📝 License
MIT
EOF

git init
git add .
git commit -m "Initial commit — PostPilot Social Media Automation"
gh repo create postpilot --public --source=. --push
