# Mantis Outreach Tool
### Mark Wroblewski — HubSpot & Front-End Developer Outreach Assistant

---

## What this is
A private AI-powered outreach tool that:
- Finds real companies hiring HubSpot or front-end developers (live web search)
- Researches individual prospects with AI
- Writes personalized cold emails + LinkedIn DMs as you
- Tracks prospects with status updates (localStorage)

---

## Deploy to Vercel (5 minutes, free)

### Step 1 — Get your Anthropic API key
1. Go to https://console.anthropic.com
2. API Keys → Create key
3. Copy it

### Step 2 — Deploy
Option A: GitHub (recommended)
1. Push this folder to a GitHub repo (can be private)
2. Go to https://vercel.com → New Project → Import your repo
3. Click Deploy (no build settings needed)

Option B: Vercel CLI
```bash
npm i -g vercel
cd mark-outreach-tool
vercel
```

### Step 3 — Add your API key
1. In Vercel dashboard → Your project → Settings → Environment Variables
2. Add: `ANTHROPIC_API_KEY` = your key from Step 1
3. Redeploy (Deployments → Redeploy)

### Step 4 — Open your tool
Vercel gives you a URL like `https://your-project.vercel.app`
Bookmark it. Done.

---

## File structure
```
mark-outreach-tool/
├── index.html        ← the entire app (UI + logic)
├── api/
│   └── claude.js     ← serverless proxy (keeps API key secret)
├── vercel.json       ← Vercel config
└── README.md
```

---

## Optional: Password protect it
In Vercel → Settings → Deployment Protection → Enable password protection.
Keeps it private to just you.

---

## Data storage
Prospect data saves to your browser's localStorage.
It persists across sessions on the same device/browser.
To back up: open browser console and run:
```javascript
copy(localStorage.getItem('mw_prospects_v1'))
```
Then paste into a text file.
