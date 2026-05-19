# RWS Auto Post 🚀

Roz automatically Instagram + Facebook pe post karta hai.

## Setup

### 1. GitHub pe push karo
```bash
git init
git add .
git commit -m "RWS auto post setup"
git remote add origin https://github.com/YOUR_USERNAME/rws-auto-post.git
git push -u origin main
```

### 2. Vercel pe deploy karo
- vercel.com pe jao
- "New Project" → GitHub repo select karo
- Deploy karo

### 3. Environment Variables add karo
Vercel Dashboard → Project → Settings → Environment Variables mein ye sab add karo:

| Variable | Value |
|----------|-------|
| ANTHROPIC_API_KEY | Claude API key |
| IMGBB_KEY | 23f5625fc2c03287e5265ca18a3873f0 |
| FB_PAGE_TOKEN | EAAefUqg... |
| FB_PAGE_ID | 101061456719064 |
| IG_USER_ID | 17841400589714454 |
| BRAND_NAME | Rudraksh Web Institute |
| BRAND_PRODUCT | Web Design & Digital Marketing Courses |
| BRAND_TAGLINE | Learn. Grow. Succeed. |
| PRIMARY_COLOR | #6C3EF4 |
| ACCENT_COLOR | #FF6B35 |
| BG_COLOR | #0F0A1E |
| CRON_SECRET | rws2024secret |

### 4. Cron Job
`vercel.json` mein schedule set hai: roz **9:30 AM IST** (4:00 UTC)

### 5. Manual Test
```
curl -X POST https://your-project.vercel.app/api/post \
  -H "Authorization: Bearer rws2024secret"
```

## Flow
1. ⏰ Roz 9:30 AM automatically trigger
2. 🤖 Claude API se fresh content generate
3. 🖼️ Banner image create (@vercel/og)
4. 📤 imgbb pe upload
5. 📘 Facebook Page pe post
6. 📸 Instagram Business pe post
