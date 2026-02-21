# Chatbot Template

> A beautiful, customizable AI chatbot interface with real-time responses!

## ✨ Features

- **Beautiful UI** — Modern chat interface with smooth animations
- **Custom Cursor** — Following cursor effect
- **Typing Indicators** — Shows when bot is "thinking"
- **Quick Actions** — Pre-built buttons for common questions
- **Message Animations** — Smooth fade-in effects
- **Auto-resize Input** — Textarea grows with content
- **Responsive Design** — Works on mobile and desktop
- **Easy Customization** — Change name, personality, responses
- **Single File** — Everything in one HTML file

---

## 🎮 How to Use

1. Open `index.html` in browser
2. Type a message or click quick action buttons
3. Bot responds with simulated answers

---

## 🚀 Quick Start

### Option 1: Manual Setup

1. Copy `index.html` to your computer
2. Edit `botConfig` in JavaScript (see below)
3. Open in browser!

### Option 2: AI-Assisted

Tell Claude Code:
```
Customize my chatbot:
- Name: "Alex Helper"
- Personality: funny and helpful
- Add responses for: 'weather', 'news', 'sports'
```

---

## 📝 Manual Customization

### 1. Change Bot Name & Avatar

Find `botConfig` in JavaScript:

```javascript
const botConfig = {
  name: "Your Assistant",    // Change this
  avatar: "🤖",              // Change emoji or use 🧙‍♂️, 👾, etc.
  // ...
};
```

### 2. Change Bot Personality

```javascript
const botConfig = {
  personality: "helpful, friendly, and knowledgeable",
  // Change to: "sarcastic and witty"
  // Or: "professional and formal"
};
```

### 3. Add Custom Responses

```javascript
const botConfig = {
  responses: {
    // Add new keywords
    greeting: ["Hello!", "Hi there!", "Hey!"],
    
    // Add new response
    weather: "I'm just a simple bot, but I hope it's sunny where you are!",
    
    // Modify existing
    help: "I can help with coding, questions, and more!"
  }
};
```

### 4. Add Keywords to Responses

Find `getBotResponse()` function:

```javascript
// Add new keyword response:
if (lower.includes('weather')) {
  return "I hope it's sunny where you are!";
}

if (lower.includes('coffee') || lower.includes('cafe')) {
  return "I don't drink coffee, but I hear it's great for coding!";
}
```

### 5. Change Colors

Find `:root` in CSS:

```css
:root {
  --accent: #ff6b9d;          /* Main color */
  --accent-secondary: #4af0e8; /* Secondary */
  --bg-primary: #06060b;      /* Background */
}
```

---

## 🤖 Connect to Real AI (Ollama)

The template works in demo mode. To connect to real AI:

### Step 1: Start Ollama

```bash
ollama serve
ollama pull llama3.2
```

### Step 2: Replace getBotResponse

Find `getBotResponse()` and replace with:

```javascript
async function getBotResponse(input) {
  try {
    const response = await fetch('http://localhost:11434/api/generate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        model: 'llama3.2',
        prompt: `You are ${botConfig.name}, ${botConfig.personality}.
                 ${botConfig.backstory}
                 
                 User: ${input}
                 
                 Response:`,
        stream: false
      })
    });
    
    const data = await response.json();
    return data.response;
  } catch (error) {
    return "Ollama isn't running. Start with: ollama serve";
  }
}
```

### Step 3: Update sendMessage

Change `sendMessage` to async:

```javascript
async function sendMessage() {
  const text = chatInput.value.trim();
  if (!text) return;

  welcomeMessage.style.display = 'none';
  addMessage(text, 'user');
  chatInput.value = '';
  
  showTyping();
  
  // Get real AI response
  const response = await getBotResponse(text);
  
  hideTyping();
  addMessage(response, 'bot');
}
```

---

## 🎨 Color Themes

| Theme | Pink | Cyan | Background |
|-------|------|------|------------|
| Pink/Cyan | #ff6b9d | #4af0e8 | #06060b |
| Purple | #a855f7 | #8b5cf6 | #0f0f1a |
| Orange | #f97316 | #fb923c | #0a0a0f |
| Green | #22c55e | #4ade80 | #0a0f0a |
| Fire | #ef4444 | #f97316 | #0a0a0a |

---

## 🤖 AI Customization Guide

### Using Claude Code

```
Update my chatbot:
- Name: "Tech Helper"
- Add these responses:
  - Keywords: ['python', 'code']
    Response: "I love Python! Great for beginners..."
  - Keywords: ['game', 'gaming']
    Response: "Games are awesome! What type..."
- Change colors to purple theme
```

### Using Ollama

```bash
ollama run llama3.2

# Ask:
"Generate JavaScript code to add a 'news' response 
keyword to my chatbot that returns current news"
```

---

## 📋 Configuration Reference

### botConfig Options

| Option | Type | Description |
|--------|------|-------------|
| `name` | string | Bot display name |
| `avatar` | string | Bot emoji avatar |
| `personality` | string | Bot personality description |
| `skills` | array | List of things bot can do |
| `backstory` | string | Bot origin story |
| `responses` | object | Keyword-response pairs |

### Response Keywords

| Keyword | Trigger |
|---------|---------|
| `greeting` | hi, hello, hey |
| `about` | who are you, about |
| `help` | help, what can you do |
| `name` | your name |
| `joke` | joke, funny |

---

## 🌐 Hosting

### Option 1: Netlify Drop
1. https://app.netlify.com/drop
2. Drag folder
3. Done!

### Option 2: Embed in Website
Copy the HTML into any website as an iframe:

```html
<iframe src="https://your-site.com/chatbot/" 
        width="100%" height="600"></iframe>
```

---

## ✅ Checklist

- [ ] Tested the chatbot
- [ ] Changed bot name
- [ ] Updated personality
- [ ] Added custom responses
- [ ] Changed colors (if wanted)
- [ ] (Optional) Connected to Ollama
- [ ] Deployed to web!

---

## 📁 File Structure

```
chatbot-template/
└── index.html    ← Single file, everything included!
```

---

## 🆘 Troubleshooting

**Bot not responding?**
- Check `botConfig` is properly formatted
- Make sure JSON is valid

**Ollama not connecting?**
- Run `ollama serve` in terminal
- Check URL is correct

**Cursor not showing?**
- Normal on touch devices

---

## 🎉 Next Steps

- Connect to OpenAI API
- Add voice input
- Add image generation
- Add file upload
- Add conversation history

---

## 📝 License

MIT — Use it however you like!

---

**Made with ❤️ and AI**
