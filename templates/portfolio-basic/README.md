# Portfolio Basic Template

> A beautiful, interactive portfolio template with custom cursor, animations, and modern design.

## ✨ Features

- **Custom Cursor** — Smooth following cursor with hover effects
- **Animated Background** — Floating orbs + starfield canvas
- **Scroll Reveal** — Elements animate in as you scroll
- **Hover Effects** — Cards lift and glow on hover
- **Clean & Modern** — Easy to read, stands out
- **Single File** — Everything in one HTML file
- **No Dependencies** — Just open in browser!

---

## 🚀 Quick Start

### Option 1: Manual Setup (No AI)

1. Copy `index.html` to your computer
2. Open in any text editor (VS Code recommended)
3. Edit your info (see sections below)
4. Open in browser to preview

### Option 2: AI-Assisted Setup (Recommended!)

Use **Claude Code** or **Ollama** to customize faster:

```bash
# Tell AI what you want:
"I want a portfolio for a Python developer in Tokyo. 
Update the colors to purple/blue theme.
Change skills to: Python, FastAPI, PostgreSQL."
```

See the **AI Setup Guide** section below for details!

---

## 📝 Manual Customization Guide

### 1. Change Your Name

Find and replace:
```html
<!-- Header -->
<a href="#" class="logo">Your<span>Name</span></a>

<!-- Hero -->
<h1><span class="line gradient">Your Name</span></h1>

<!-- Footer -->
<p>© 2026 Your Name.</p>
```

### 2. Change Colors

Find `:root` at the top of the CSS and modify:

```css
:root {
  --accent: #ff6b9d;          /* Pink - main accent */
  --accent-secondary: #4af0e8; /* Cyan - secondary */
  --bg-primary: #06060b;     /* Dark background */
  --bg-card: #10101a;         /* Card background */
}
```

**Color Themes:**

| Theme | Pink | Cyan | Background |
|-------|------|------|------------|
| Pink/Cyan (default) | #ff6b9d | #4af0e8 | #06060b |
| Purple | #a855f7 | #8b5cf6 | #0f0f1a |
| Orange | #f97316 | #fb923c | #0a0a0f |
| Green | #22c55e | #4ade80 | #0a0f0a |
| Monochrome | #ffffff | #94a3b8 | #0a0a0a |

### 3. Change Profile Image

Replace the emoji:
```html
<div class="about-image">👨‍💻</div>
```

With your image:
```html
<div class="about-image">
  <img src="your-photo.jpg" alt="Your Name" style="width:100%;height:100%;object-fit:cover;border-radius:24px;">
</div>
```

### 4. Update Skills

Find the `skills-grid` section:
```html
<div class="skill-card">
  <span class="skill-icon">🌐</span>
  <h3>Web Development</h3>
  <p>Building modern websites.</p>
</div>
```

Add/remove cards as needed.

### 5. Update Projects

Find the `projects-grid` and modify:
```html
<div class="project-card">
  <div class="project-image">
    <span class="project-icon">🚀</span>
  </div>
  <div class="project-info">
    <h3>Project Name</h3>
    <p>Description here.</p>
    <div class="project-tags">
      <span class="tag">React</span>
    </div>
  </div>
</div>
```

### 6. Update Contact Links

```html
<a href="mailto:your@email.com" class="contact-card">
<a href="https://github.com/yourusername" target="_blank">
<a href="https://twitter.com/yourusername" target="_blank">
<a href="https://linkedin.com/in/yourusername" target="_blank">
```

### 7. Change "Available for work" Badge

```html
<div class="hero-badge">
  <span>Available for work</span>
</div>
```

---

## 🤖 AI Setup Guide

### Prerequisites

Install these free tools:

1. **Ollama** (for local AI)
   - Download: https://ollama.com
   - Run: `ollama serve`
   - Install model: `ollama pull llama3.2`

2. **Claude Code** (optional, for coding help)
   - https://claude.com/claude-code

### Using AI to Customize

#### Method 1: Ask Ollama Directly

```bash
# Start Ollama first
ollama serve

# In another terminal, use prompt engineering:
ollama run llama3.2 "Create HTML code for a skill card with icon, title and description"
```

#### Method 2: Use Claude Code

Tell Claude what you want:

```
Update my portfolio with:
- Name: "Alex Chen"
- Location: "San Francisco"
- Skills: Python, JavaScript, React, AWS
- Accent color: #8b5cf6 (purple)
- Add 2 more project cards
```

#### Method 3: Custom AI Prompts

Here's a prompt you can use with any AI:

```
I'm using a portfolio template with this structure:
- CSS variables in :root for colors
- Sections: hero, about, skills, projects, contact
- Grid layouts for cards

Generate the HTML to:
1. Change name to [YOUR NAME]
2. Update skills to: [YOUR SKILLS]
3. Update projects with: [YOUR PROJECTS]
4. Keep the same design style but change colors to: [YOUR COLORS]

Only output the modified HTML sections, not the full file.
```

### AI-Powered Customization Examples

**Change colors with AI:**
```
Replace the :root CSS variables in my portfolio to use:
- Primary: #7c3aed (purple)
- Secondary: #06b6d4 (cyan)
- Background: #0f0f1a
```

**Add projects with AI:**
```
Generate 3 project card HTML with these projects:
1. "Task App" - React todo app - tags: React, TypeScript
2. "Weather Bot" - Python Discord bot - tags: Python, API
3. "Portfolio" - Personal site - tags: HTML, CSS
```

---

## 🎨 Customization Reference

### CSS Variables

| Variable | Purpose | Example |
|----------|---------|---------|
| `--accent` | Main color | #ff6b9d |
| `--accent-secondary` | Secondary | #4af0e8 |
| `--bg-primary` | Page background | #06060b |
| `--bg-card` | Card background | #10101a |
| `--text-primary` | Main text | #f4f4f6 |
| `--text-secondary` | Muted text | #9898a8 |

### Animation Classes

- `.reveal` — Add to elements for scroll animation
- `.hover-target` — Add to interactive elements for cursor effect

---

## 🌐 Hosting

### Option 1: Netlify Drop (Easiest)
1. Go to https://app.netlify.com/drop
2. Drag your folder (containing index.html)
3. Get free URL instantly!

### Option 2: GitHub Pages
1. Create repository
2. Upload index.html
3. Settings → Pages → Enable

### Option 3: Vercel
```bash
npm i -g vercel
vercel
```

---

## ✅ Checklist Before Publish

- [ ] Changed name
- [ ] Updated bio/about section
- [ ] Added your real projects
- [ ] Updated contact links
- [ ] Changed colors (if wanted)
- [ ] Tested on mobile
- [ ] Deployed to web!

---

## 📁 File Structure

```
portfolio-basic/
└── index.html    ← Single file, everything included!
```

---

## 🆘 Troubleshooting

**Cursor not showing?**
- You're on touch device — cursor隐藏 automatically on mobile

**Animations not working?**
- Check JavaScript is enabled
- Try a different browser

**Images not loading?**
- Check file path is correct
- Use absolute URLs: `/images/photo.jpg`

---

## 📝 License

MIT — Use it however you like!

---

**Made with ❤️ and AI**
