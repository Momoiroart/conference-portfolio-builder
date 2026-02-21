# Portfolio AI Template

> An AI-powered portfolio with a built-in chat widget that can answer questions about you!

## ✨ Features

- **AI Chat Widget** — Visitors can chat with an AI that knows about you
- **Demo Mode** — Works out of the box with simple JSON config
- **Ollama Ready** — Can connect to local Ollama for real AI responses
- **Code Section** — Show off your code with syntax highlighting
- **Modern Design** — Dark theme with pink/cyan accents
- **Responsive** — Works on mobile and desktop
- **Single File** — Everything in one HTML file

## 🚀 Quick Start

### Step 1: Copy the Template
Copy `index.html` to your computer.

### Step 2: Edit Your Info
Find the `portfolioData` object in the script and edit:

```javascript
const portfolioData = {
  name: "Your Name",
  location: "Your City",
  skills: ["Web Dev", "Python", "AI"],
  projects: [
    { name: "Project One", description: "...", tags: ["React"] }
  ],
  interests: ["coding", "games"],
  contact: "your@email.com"
};
```

### Step 3: Customize Colors
Find `:root` at the top of CSS:

```css
:root {
  --accent: #ff6b9d;        /* Pink */
  --accent-secondary: #4af0e8; /* Cyan */
}
```

### Step 4: Open in Browser
Double-click `index.html` to preview!

## 🤖 Connecting to Real AI (Ollama)

The template comes with **demo mode** (fake AI responses). To connect to real Ollama:

### Option 1: Local Ollama API

Replace the `sendMessage` function with:

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
        model: 'llama3.2',  // or any model you have
        prompt: `You are a helpful assistant for ${portfolioData.name}'s portfolio. 
                 The owner is based in ${portfolioData.location}.
                 Their skills: ${portfolioData.skills.join(', ')}.
                 Their projects: ${portfolioData.projects.map(p => p.name + ': ' + p.description).join(', ')}.
                 
                 User question: ${text}
                 
                 Give a friendly, brief answer:`,
        stream: false
      })
    });
    
    const data = await response.json();
    typingIndicator.classList.remove('active');
    addMessage(data.response);
  } catch (error) {
    typingIndicator.classList.remove('active');
    addMessage("Ollama isn't running! Start it with: ollama serve");
  }
}
```

### Option 2: Use Claude/OpenAI API

```javascript
async function sendMessage() {
  const text = chatInput.value.trim();
  if (!text) return;

  addMessage(text, true);
  chatInput.value = '';
  typingIndicator.classList.add('active');

  // Replace with your API call
  const response = await fetch('https://api.openai.com/v1/chat/completions', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'Authorization': 'Bearer YOUR_API_KEY'
    },
    body: JSON.stringify({
      model: 'gpt-4',
      messages: [{
        role: 'system',
        content: `You are ${portfolioData.name}'s portfolio assistant.`
      }, {
        role: 'user',
        content: text
      }]
    })
  });

  const data = await response.json();
  typingIndicator.classList.remove('active');
  addMessage(data.choices[0].message.content);
}
```

## 📝 What to Edit

| Section | Find | Change To |
|---------|------|-----------|
| Name/Info | `portfolioData` object | Your details |
| Colors | `:root` CSS variables | Your colors |
| Skills | `skills-grid` section | Your skills |
| Projects | `projects-grid` section | Your projects |
| Code | `code-section` | Your code samples |
| Contact | `contact-grid` section | Your links |

## 🎨 Color Themes

| Theme | Pink | Cyan |
|-------|------|------|
| Default | `#ff6b9d` | `#4af0e8` |
| Purple | `#9b59b6` | `#3498db` |
| Sunset | `#e74c3c` | `#f39c12` |
| Forest | `#27ae60` | `#1abc9c` |

## 🌐 Hosting

Same as basic template — drag folder to Netlify Drop!

## 📁 File Structure

```
portfolio-ai/
└── index.html    ← Single file, everything included
```

## 🔧 Advanced: Custom AI Responses

Add more keywords to the `responses` array:

```javascript
{
  keywords: ['hobby', 'free time', 'fun'],
  response: "When not coding, they enjoy gaming and hiking!"
}
```

## ✅ Checklist

- [ ] Updated portfolioData with your info
- [ ] Changed colors if wanted
- [ ] Added your real projects
- [ ] Updated contact links
- [ ] Tested chat widget
- [ ] (Optional) Connected to Ollama

## 📝 License

MIT — Use it however you like!

---

**Made with ❤️ using Claude Code + Ollama**
