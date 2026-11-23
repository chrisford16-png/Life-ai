# LIFE AI — v4 Real AI PWA

LIFE AI is an installable Progressive Web App for Android and desktop browsers. It is designed to remain free for end users.

## Included
- Responsive LIFE AI dashboard
- Real AI chat through a server-side API route (after configuration)
- AI-powered Business Builder, Idea Studio, and Learning Center
- Chat history, tasks, and notes stored locally in the browser
- Optional browser voice input and spoken-reply helper
- Installable PWA manifest and offline app shell
- API key kept on the server, never in browser JavaScript
- Basic security headers and request validation

## Important cost and launch facts
Free for users does **not** mean free to operate. AI provider usage and hosting can incur charges. The app owner pays those charges unless a sponsor funds them. Set provider spending limits and alerts before public launch. Do not promise unlimited AI usage.

This package does not contain an API key, a Vercel account, a deployed domain, a shared production rate limiter, user accounts, or cloud synchronization. The in-memory request guard is only a prototype safeguard: serverless instances do not share memory. Add a shared rate limiter, abuse monitoring, budget alerts, a privacy notice, and retention rules before public launch.

## Deploy on Vercel
1. Put these project files in a Git repository and import it into Vercel, or deploy using the Vercel CLI.
2. In Vercel Project Settings → Environment Variables, add:
   - `OPENAI_API_KEY` — your private provider API key
   - `OPENAI_MODEL` — `gpt-4.1-mini` (or a model enabled for your API account)
3. Redeploy after adding environment variables.
4. Open the HTTPS deployment and test chat, Business Builder, Idea Studio, and Learning Center.
5. On Android Chrome, use the browser menu and choose **Install app** or **Add to Home screen**.

Never put the API key in `index.html`, `sw.js`, a public repository, or a message.

## Local test
Use Node.js 20+ and Vercel CLI:
```bash
npm install -g vercel
vercel dev
```
Set `OPENAI_API_KEY` in your local environment or a private `.env.local` file (never commit it).

## Privacy
Tasks, notes, and chat history are stored in local browser storage on the device. They are not synced between devices. Clearing browser data may erase them. Do not enter highly sensitive information. Browser voice input may be processed by the device/browser speech service and availability varies by browser.

## Current limits
- The live AI requires the owner to configure a valid API key and deploy the server route.
- AI provider calls can cost money; the app is free to users only if the owner funds operation.
- No sign-in, cloud sync, multi-device backup, native Play Store package, or production-grade shared rate limiting is included yet.


## Vercel project settings
- Framework Preset: **Other**
- Root Directory: repository root (the folder containing `index.html` and `vercel.json`)
- Build Command: leave blank
- Output Directory: leave blank
- Install Command: leave blank (no build dependencies are required)
- Node.js runtime: use Node.js 20 or newer
