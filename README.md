# LearnHub — Static HTML Site

Free static site with topics, subtopics, and a working contact form.
No framework, no build step — just plain HTML + CSS files.

---

## File Structure

```
learnhub-static/
├── index.html              ← Home page
├── contact.html            ← Contact form (email via Netlify Forms)
├── css/
│   └── style.css           ← All styles (edit colors/fonts here)
├── topics/
│   ├── ccna.html           ← CCNA topic index
│   ├── linux.html          ← Linux topic index
│   ├── python.html         ← Python topic index
│   ├── ccna/
│   │   ├── network-fundamentals.html
│   │   ├── ip-addressing.html
│   │   ├── routing.html
│   │   ├── vlans.html
│   │   ├── acls.html
│   │   └── nat.html
│   ├── linux/
│   │   ├── file-system.html
│   │   ├── permissions.html
│   │   └── ...
│   └── python/
│       ├── basics.html
│       └── ...
└── netlify.toml            ← Netlify config
```

---

## How to add a new subtopic

1. Copy any existing subtopic file, e.g. `topics/ccna/nat.html`
2. Rename it, e.g. `topics/ccna/wireless.html`
3. Edit the title, heading and content inside the file
4. Add a link to it in `topics/ccna.html` (the topic index page)
5. Add it to the sidebar list in your new file

That's it — no build step, no commands needed.

---

## Upload to GitHub

### Option A — GitHub Website (easiest)
1. Go to https://github.com → Create free account
2. Click "+" → New repository → Name it `learnhub` → Create
3. Click "uploading an existing file"
4. Drag and drop ALL files from the `learnhub-static` folder
5. Click "Commit changes"
6. Repeat if you have more files (GitHub web upload has limits)

### Option B — Git Terminal (best for regular updates)
```bash
cd learnhub-static

git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/learnhub.git
git push -u origin main
```

Then for every content update:
```bash
git add .
git commit -m "added new CCNA subtopic"
git push
```

---

## Deploy FREE on Netlify

1. Go to https://app.netlify.com → Sign up free (use GitHub)
2. Click "Add new site" → "Import an existing project"
3. Connect GitHub → select your `learnhub` repo
4. Settings (auto-detected from netlify.toml):
   - Build command: *(leave empty)*
   - Publish directory: `.`
5. Click "Deploy site"

Live in ~30 seconds at: https://your-site-name.netlify.app

---

## Set Up Contact Form Email (FREE)

The contact form uses Netlify Forms — completely free, no backend needed.

### Steps after deploying:
1. Go to Netlify Dashboard → your site
2. Click "Forms" tab in the top menu
3. You'll see the "contact" form listed after the first submission
4. Click "Form notifications" → "Add notification" → "Email notification"
5. Enter YOUR email address
6. Click Save

Now every contact form submission arrives in your inbox. Free forever (up to 100 submissions/month on free plan).

---

## Update content

Edit any .html file directly and push to GitHub.
Netlify auto-rebuilds (actually just re-publishes the files) in ~10 seconds.

```bash
# Edit topics/ccna/routing.html in any text editor, then:
git add .
git commit -m "updated routing notes"
git push
# Site updates in 10 seconds ✅
```

---

## Custom domain

1. Netlify Dashboard → your site → "Domain settings"
2. "Add custom domain" → type your domain
3. Update your domain DNS nameservers to Netlify's (shown on screen)
4. Free SSL (HTTPS) added automatically in minutes
