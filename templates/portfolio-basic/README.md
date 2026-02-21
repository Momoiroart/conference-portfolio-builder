# Portfolio Basic Template

> A simple, beginner-friendly portfolio template. No frameworks, just pure HTML & CSS!

## ✨ Features

- **Beginner Friendly** — Just edit the text and go!
- **Single File** — Everything in one HTML file
- **Responsive** — Looks great on phone & desktop
- **Dark Theme** — Modern dark design with pink/cyan accents
- **Animations** — Smooth scroll & fade-in effects
- **No Setup** — Open directly in browser

## 🚀 How to Use

### Step 1: Copy the Template
Copy `index.html` to your computer anywhere you like.

### Step 2: Edit Your Info
Open `index.html` in any text editor (Notepad, VS Code, etc.) and change:

```html
<!-- Change these: -->
<title>My Portfolio</title>
<h1>Your Name<br><span>Creator & Designer</span></h1>
<p>your@email.com</p>
```

### Step 3: Customize Colors (Optional)
Find the `:root` section at the top of the CSS and change colors:

```css
:root {
  --accent: #ff6b9d;        /* Change pink */
  --accent-secondary: #4af0e8; /* Change cyan */
  --bg-primary: #0a0a0f;    /* Change background */
}
```

### Step 4: Add Your Images
Replace the emoji placeholders with real images:

```html
<!-- Replace this: -->
<div class="about-image">📸</div>

<!-- With this: -->
<img src="your-photo.jpg" alt="Your Name" class="about-image">
```

### Step 5: Open in Browser
Double-click `index.html` to preview!

## 📝 What to Edit

| Section | Find | Change To |
|---------|------|-----------|
| Name | `<a class="logo">YourName</a>` | Your name |
| Hero | `<h1>Your Name<br><span>...</span></h1>` | Your intro |
| About | `<p>Hi! I'm...</p>` | Your bio |
| Skills | `<div class="skill-card">` | Your skills |
| Projects | `<div class="project-card">` | Your projects |
| Contact | `href="mailto:your@email.com"` | Your links |

## 🎨 Color Ideas

| Vibe | Pink | Cyan |
|------|------|------|
| Default | `#ff6b9d` | `#4af0e8` |
| Purple | `#9b59b6` | `#3498db` |
| Orange | `#e67e22` | `#f39c12` |
| Green | `#2ecc71` | `#1abc9c` |
| Monochrome | `#ffffff` | `#888888` |

## 🌐 Hosting for Free

### Option 1: Netlify Drop
1. Go to https://app.netlify.com/drop
2. Drag your folder (containing index.html) 
3. Done! Get your free URL instantly

### Option 2: GitHub Pages
1. Create a repo on GitHub
2. Upload index.html
3. Go to Settings → Pages → Enable GitHub Pages

### Option 3: Vercel
1. Install Vercel CLI: `npm i -g vercel`
2. Run `vercel` in your folder
3. Follow prompts

## 📚 What's Inside

- **Header** — Logo + navigation
- **Hero** — Big headline + CTA buttons
- **About** — Your photo + bio
- **Skills** — 4 skill cards
- **Projects** — 3 project cards with tags
- **Contact** — Email, GitHub, Twitter links
- **Footer** — Copyright

## 🤖 Want AI Features?

This is the **basic** version. For AI-powered portfolios with:
- Chat with visitors
- AI-generated content
- Smart recommendations

Check out the **Portfolio AI** template in this folder!

## 📁 File Structure

```
portfolio-basic/
└── index.html    ← That's it! Just one file.
```

## ✅ Checklist Before Publishing

- [ ] Changed name to yours
- [ ] Updated bio/about section
- [ ] Added your real projects
- [ ] Changed email to yours
- [ ] Added your social links
- [ ] Tested on mobile
- [ ] Deployed to the web!

## 🆘 Need Help?

1. **It's not showing right** — Clear browser cache (Ctrl+Shift+R)
2. **Images not loading** — Check file path is correct
3. **Colors look wrong** — Make sure to edit the `:root` section

## 📝 License

MIT — Use it however you like!

---

**Made with ❤️ using Claude Code + Ollama**
