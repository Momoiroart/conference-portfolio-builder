# AI Setup Tutorial

> Use AI tools (Ollama + Claude Code) to build your portfolio faster and smarter!

## What You'll Learn

- Install and use Ollama (free local AI)
- Use Claude Code to customize your portfolio
- Connect AI chat widget to real Ollama
- Generate content with AI

## Prerequisites

- Computer (Windows/Mac/Linux)
- 30-45 minutes

---

## Part 1: Install Ollama

Ollama is a free tool that runs AI locally on your computer. No internet needed after installation!

### Step 1.1: Download Ollama

1. Go to: https://ollama.com
2. Click **Download** for your operating system
3. Run the installer

### Step 1.2: Install a Model

After installing, open terminal (Command Prompt on Windows) and run:

```bash
# This downloads the AI model (about 2-4GB)
ollama pull llama3.2
```

### Step 1.3: Test Ollama

```bash
# Should respond with version
ollama --version

# Start Ollama server
ollama serve
```

Keep Ollama running while working!

---

## Part 2: Install Claude Code (Optional)

Claude Code is an AI coding assistant that can help you build faster.

### Step 2.1: Download

1. Go to: https://claude.com/claude-code
2. Download for your OS
3. Install and sign in

### Step 2.2: Basic Commands

```bash
# Ask Claude to help
claude "Update my portfolio colors to purple"

# Or use in the chat interface
```

---

## Part 3: Customize with AI

### Method A: Using Claude Code

Open your terminal in the portfolio folder and ask:

```
Update my portfolio with:
- Name: "Alex Chen"
- Location: "Tokyo, Japan"
- Skills: Python, JavaScript, Unity, Blender
- Projects: 
  1. "TaskMaster" - React todo app
  2. "GameAI" - Python game
  3. "Portfolio" - Personal site
- Colors: Purple theme (#a855f7, #8b5cf6)
```

Claude will update your HTML file!

### Method B: Using Ollama Directly

```bash
# In terminal with Ollama running
ollama run llama3.2

# Then ask:
"Generate HTML for a skill card with icon 🎮, title 'Game Dev', 
description 'Creating games with Unity'"
```

### Method C: Using AI Prompts

Copy/paste these prompts into Claude or Ollama:

**Change colors:**
```
Replace the :root CSS variables in portfolio-basic/index.html with:
- --accent: #a855f7 (purple)
- --accent-secondary: #8b5cf6 (light purple)
- --bg-primary: #0f0f1a (dark purple bg)
- --bg-card: #1a1a2e (card bg)
```

**Add projects:**
```
Generate HTML for 3 project cards with:
1. "Weather App" - React app showing weather - tags: React, API
2. "Chat Bot" - Python Discord bot - tags: Python, AI  
3. "Portfolio" - This portfolio - tags: HTML, CSS
```

---

## Part 4: Connect AI Chat Widget

The portfolio has a built-in AI chat. Here's how to connect it to Ollama!

### Step 4.1: Open the HTML File

Open `portfolio-ai/index.html` in your text editor

### Step 4.2: Find the sendMessage Function

Search for this section in the JavaScript:

```javascript
async function sendMessage() {
  const text = chatInput.value.trim();
  if (!text) return;

  addMessage(text, true);
  chatInput.value = '';
  // ... rest of function
}
```

### Step 4.3: Replace with Ollama Integration

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
        prompt: `You are ${portfolioData.name}'s portfolio AI assistant.
                 Owner is based in ${portfolioData.location}.
                 Skills: ${portfolioData.skills.join(', ')}.
                 Projects: ${portfolioData.projects.map(p => p.name + ': ' + p.description).join(', ')}.
                 
                 User asked: ${text}
                 
                 Give a friendly, helpful answer:`,
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

### Step 4.4: Make Sure Ollama is Running

```bash
# Terminal 1
ollama serve

# Terminal 2
# Open portfolio in browser and test chat!
```

---

## Part 5: AI Content Generation

### Generate Project Descriptions

Prompt:
```
Write 3 short project descriptions (1 sentence each) for a developer who made:
1. A todo app with React
2. A weather bot with Python
3. A portfolio website
```

### Generate Skills List

Prompt:
```
List 8 web development skills as JSON:
["skill name", "description"]
```

### Generate About Bio

Prompt:
```
Write a 3-paragraph developer bio for someone named Alex who:
- Is from Tokyo
- Knows Python, React, Unity
- Loves game development
- Lives in San Francisco now
```

---

## Troubleshooting

### Ollama not starting?
```bash
# Check if it's running
tasklist | findstr ollama

# Or on Mac
ps aux | grep ollama
```

### Chat not connecting?
1. Make sure Ollama is running (`ollama serve`)
2. Check the URL is `http://localhost:11434`
3. Try: `curl http://localhost:11434`

### Claude Code not working?
- Make sure you're in the project folder
- Try: `claude "help me edit index.html"`

---

## 🎉 You're Done!

Now you know how to use AI to:
- ✅ Customize your portfolio
- ✅ Connect the AI chat widget
- ✅ Generate content

**Next:**
- Deploy your portfolio!
- Share with friends!
- Keep learning AI tools!

---

## Learn More

- Ollama docs: https://github.com/ollama/ollama
- Claude Code: https://claude.com/claude-code

---

[← Back to Portfolio Builder](../README.md)
