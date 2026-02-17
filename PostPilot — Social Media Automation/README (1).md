# 🚀 PostPilot — Social Media Automation & Content Scheduler

A full-featured social media scheduling and automation dashboard with AI content generation, visual content calendar, multi-platform posting, and hashtag management — similar to Buffer or Later.

## 🚀 Features

- **Multi-Platform Composer** — Schedule posts to Twitter/X, LinkedIn, Instagram, Facebook, and YouTube simultaneously
- **Visual Content Calendar** — Monthly calendar grid showing all scheduled posts with color-coded platform chips
- **AI Content Generation** — Typewriter-effect AI writer, content improver, shortener, and hashtag suggester
- **Smart Scheduling** — "Best Times" quick-set buttons based on engagement data
- **Hashtag Manager** — Tag input with visual hashtag pills
- **Queue Manager** — Upcoming posts list with delete, reorder, and preview
- **Live Stats** — Animated counters for posts, impressions, engagement, and queue size
- **Post Preview** — In-panel preview before scheduling
- **Draft Saving** — Save work-in-progress without scheduling

## 🛠 Tech Stack

- Single-file HTML/CSS/JS — zero dependencies
- Typewriter animation for AI generation
- CSS Grid for calendar layout
- requestAnimationFrame number animations
- Google Fonts: Bricolage Grotesque + Azeret Mono

## 📂 File Structure

```
05-social-media-automation/
├── index.html    # Complete application
└── README.md     # This file
```

## 🏃 Quick Start

```bash
open index.html
```

## 💡 How to Demo

1. Click **✦ AI Write** to generate content with typewriter effect
2. Toggle **platform buttons** to select Twitter, LinkedIn, etc.
3. Click a **calendar day** to set the date
4. Click **Best Time** buttons to auto-set optimal time
5. Click **📅 Schedule Post** to add to queue and calendar
6. Browse the **Queue** at the bottom to see scheduled posts
7. Navigate months with **‹ ›** arrows

## 🔌 Production Integration

```javascript
// Real posting with platform APIs
const schedule = require('node-schedule');
const twitter = require('twitter-api-v2');
const linkedIn = require('linkedin-api');

// Schedule a post
schedule.scheduleJob(post.datetime, async () => {
  const results = await Promise.allSettled([
    post.platforms.includes('tw') && postToTwitter(post),
    post.platforms.includes('li') && postToLinkedIn(post),
    post.platforms.includes('ig') && postToInstagram(post),
  ]);
  await updatePostStatus(post.id, 'published');
  await sendNotification(`Post published to ${post.platforms.join(', ')}`);
});

// AI content generation
async function generateContent(prompt, tone) {
  const completion = await openai.chat.completions.create({
    model: 'gpt-4',
    messages: [{ role: 'user', content: `Write a ${tone} social media post about: ${prompt}` }]
  });
  return completion.choices[0].message.content;
}
```

## 🏗️ Architecture

```
Frontend Dashboard (this)
    ↓ API calls
Backend (Node.js/Express)
    ↓ schedule
Job Queue (Bull/BullMQ + Redis)
    ↓ at scheduled time
Platform APIs:
    - Twitter API v2
    - LinkedIn API
    - Instagram Graph API
    - Facebook Graph API
    - YouTube Data API
    ↓ analytics
Analytics DB (PostgreSQL/TimescaleDB)
```

## 📊 Platforms Supported

| Platform | API | Auth |
|----------|-----|------|
| Twitter/X | Twitter API v2 | OAuth 2.0 |
| LinkedIn | LinkedIn API | OAuth 2.0 |
| Instagram | Instagram Graph API | OAuth 2.0 |
| Facebook | Facebook Graph API | OAuth 2.0 |
| YouTube | YouTube Data API v3 | OAuth 2.0 |

## 🤖 AI Features

- **AI Write** — Full post generation with typewriter animation
- **Improve** — Enhance existing content with hooks and CTAs
- **Shorten** — Trim to Twitter character limit
- **Hashtags** — Smart hashtag suggestions based on content topic

## 📝 License

MIT
