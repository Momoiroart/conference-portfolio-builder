# Portfolio AI Template

## 🌐 Live Demo
**https://ai-portfolio-template.netlify.app**

> 🎓 Part of the [Learn AI Guide](https://learnai-guide.netlify.app) — free templates for everyone!

> An interactive portfolio with a built-in AI chat widget that can answer questions about you!

## ✨ Features

- **AI Chat Widget** — Visitors can chat with an AI that knows about you
- **Custom Cursor** — Smooth following cursor with hover effects
- **Animated Background** — Floating orbs + starfield canvas
- **Scroll Reveal** — Elements animate in as you scroll
- **Hover Effects** — Cards lift and glow on hover
- **Code Section** — Syntax-highlighted code display
- **Clean & Modern** — Easy to read, stands out
- **Single File** — Everything in one HTML file

---

## 🚀 Quick Start

### Option 1: Manual Setup

1. Copy `index.html` to your computer
2. Open in any text editor (VS Code recommended)
3. Edit your info (see customization guide below)
4. Open in browser to preview

### Option 2: AI-Assisted Setup

Use AI tools to customize faster:

```bash
# Tell AI what you want:
"I want an AI portfolio for a game developer in Tokyo.
Update the colors to purple theme.
Change skills to: Unity, C#, Blender, Game Design."
```

See **AI Setup Guide** below!

---

## 📝 Manual Customization Guide

### 1. Change Your Name

```html
<!-- Header -->
<a href="#" class="logo">Your<span>Name</span></a>

<!-- Hero -->
<h1><span class="line gradient">Your Name</span></h1>

<!-- Footer -->
<p>© 2026 Your Name.</p>
```

### 2. Update Your Info for AI Chat

**IMPORTANT:** Edit the `portfolioData` object in the JavaScript section:

```javascript
const portfolioData = {
  name: "Your Name",
  location: "Your City",
  skills: ["Web Dev", "Python", "AI"],
  projects: [
    { name: "Project One", description: "A web app", tags: ["React"] },
    { name: "Project Two", description: "An AI tool", tags: ["Python", "Ollama"] },
    { name: "Project Three", description: "A game", tags: ["Unity", "C#"] }
  ],
  interests: ["coding", "games", "AI"],
  contact: "your@email.com"
};
```

### 3. Add Custom AI Responses

Add more keywords to the `responses` array:

```javascript
{
  keywords: ['hobby', 'fun', 'free time'],
  response: "When not coding, they enjoy gaming and hiking!"
}
```

### 4. Change Colors

Find `:root` in CSS:

```css
:root {
  --accent: #ff6b9d;          /* Pink */
  --accent-secondary: #4af0e8; /* Cyan */
  --bg-primary: #06060b;       /* Background */
}
```

### 5. Update Sections

Same as basic template — skills, projects, contact, etc.

---

## 🤖 AI Setup Guide

### Prerequisites

1. **Ollama** (free local AI)
   - Download: https://ollama.com
   - Run: `ollama serve`
   - Install: `ollama pull llama3.2`

2. **Claude Code** (optional)
   - https://claude.com/claude-code

### Connecting to Real Ollama

The template works in **Demo Mode** by default. To connect to real AI:

Find the `sendMessage` function and replace with:

```javascript
async function sendMessage() {
  const text = chatInput.value.trim();
  if (!text) return;

  addMessage(text, true);
  chatInput.value = '';
  typingIndicator.classList.add('active');

  try {
    const response = await fetch('http://localhost:11434/api/generate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        model: 'llama3.2',
        prompt: `You are a helpful assistant for ${portfolioData.name}'s portfolio.
                 Owner: ${portfolioData.name}
                 Location: ${portfolioData.location}
                 Skills: ${portfolioData.skills.join(', ')}
                 Projects: ${portfolioData.projects.map(p => p.name + ': ' + p.description).join(', ')}
                 
                 User: ${text}
                 
                 Give a friendly, brief answer:`,
        stream: false
      })
    });
    
    const data = await response.json();
    typingIndicator.classList.remove('active');
    addMessage(data.response);
  } catch (error) {
    typingIndicator.classList.remove('active');
    addMessage("Ollama isn't running. Start it with: ollama serve");
  }
}
```

### Using Claude Code for Customization

Tell Claude what you want:

```
Update my AI portfolio:
- Name: "Alex Chen"
- Skills: Unity, C#, Blender, Unreal
- Accent color: purple (#a855f7)
- Add 4 more AI responses for: 'vr', 'unreal', '3d modeling', 'animation'
```

### AI Prompt Templates

**Change everything:**
```
I want to customize my portfolio AI template with:
- Name: [YOUR NAME]
- Location: [YOUR CITY]
- Skills: [YOUR SKILLS]
- Projects: [YOUR PROJECTS]
- Colors: [YOUR COLOR THEME]

Generate the updated portfolioData object and CSS variables.
```

**Add AI responses:**
```
Add these AI responses to my portfolio:
- Keywords: ['coffee', 'cafe']
  Response: "They love coffee and often work from cafes!"
- Keywords: ['music', 'spotify']
  Response: "They listen to lo-fi while coding."
```

---

## 🎨 Customization Reference

### Color Themes

| Theme | Pink | Cyan | Background |
|-------|------|------|------------|
| Pink/Cyan | #ff6b9d | #4af0e8 | #06060b |
| Purple | #a855f7 | #8b5cf6 | #0f0f1a |
| Orange | #f97316 | #fb923c | #0a0a0f |
| Green | #22c55e | #4ade80 | #0a0f0a |

### Chat Widget Customization

**Change the floating button icon:**
```javascript
// Find this line and change the emoji
<button class="chat-toggle" onclick="toggleChat()">💬</button>
```

**Change chat colors:**
```css
.chat-window { /* chat background */ }
.message.ai { /* AI message color */ }
.message.user { /* Your message color */ }
```

---

## 🌐 Hosting

### Option 1: Netlify Drop
1. https://app.netlify.com/drop
2. Drag your folder
3. Done!

### Option 2: GitHub Pages
1. Create repo, upload files
2. Settings → Pages → Enable

### Option 3: Vercel
```bash
npm i -g vercel
vercel
```

---

## ⚠️ Important: Configure AI First!

Before publishing, make sure to:

1. ✅ Edit `portfolioData` with your real info
2. ✅ Add custom responses for common questions
3. ✅ (Optional) Connect to Ollama for real AI
4. ✅ Test the chat widget

---

## ✅ Checklist

- [ ] Updated portfolioData object
- [ ] Added custom AI responses
- [ ] Changed colors (if wanted)
- [ ] Updated all sections (about, skills, projects)
- [ ] Changed contact links
- [ ] Tested chat widget
- [ ] (Optional) Connected to Ollama
- [ ] Deployed to web!

---

## 📁 File Structure

```
portfolio-ai/
└── index.html    ← Single file with everything!
```

---

## 🆘 Troubleshooting

**Chat not working?**
- Check portfolioData is filled out
- Demo mode should work offline

**Ollama connection failed?**
- Make sure Ollama is running: `ollama serve`
- Try: `curl http://localhost:11434`

**Cursor not showing?**
- Normal on touch devices

---

## 📝 License

MIT — Use it however you like!

---

**Made with ❤️ and AI**
