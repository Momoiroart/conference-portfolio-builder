# Game Template

> A space shooter game template with stunning visuals, particles, and scoring system!

## ✨ Features

- **Complete Game** — Playable space shooter
- **Custom Cursor** — Smooth following cursor
- **Animated Background** — Floating orbs + starfield
- **Particle Effects** — Explosions and engine flames
- **Scoring System** — Points, levels, lives
- **Menu Screens** — Start, how to play, game over
- **Pause Function** — Press P to pause
- **Single File** — Everything in one HTML file
- **Easy to Customize** — Change colors, speed, gameplay

---

## 🎮 How to Play

| Control | Action |
|---------|--------|
| ← → or A/D | Move spaceship |
| SPACE | Shoot |
| P | Pause game |

**Goal:** Destroy asteroids to score points. Level up every 100 points!

---

## 🚀 Quick Start

### Option 1: Manual Setup

1. Copy `index.html` to your computer
2. Open in browser to play!
3. Edit to customize (see below)

### Option 2: AI-Assisted

Tell Claude Code or Ollama:
```
Customize my game template:
- Change colors to purple theme
- Add a boss every 5 levels
- Change player ship to triangle
```

---

## 📝 Manual Customization

### 1. Change Colors

Find `:root` at the top of CSS:

```css
:root {
  --accent: #ff6b9d;        /* Main color (pink) */
  --accent-secondary: #4af0e8; /* Secondary (cyan) */
  --bg-primary: #06060b;    /* Background */
}
```

**Color Themes:**

| Theme | Pink | Cyan | Background |
|-------|------|------|------------|
| Pink/Cyan | #ff6b9d | #4af0e8 | #06060b |
| Purple | #a855f7 | #8b5cf6 | #0f0f1a |
| Orange | #f97316 | #fb923c | #0a0a0f |
| Green | #22c55e | #4ade80 | #0a0f0a |

### 2. Change Game Title

```html
<!-- Find and change: -->
<h1 class="menu-title">Space Defender</h1>
```

### 3. Adjust Difficulty

Find these variables in JavaScript:

```javascript
// Speed settings
player.speed = 7;          // Player movement speed
bulletSpeed = 10;          // Bullet speed
enemySpeed = 2;            // Enemy speed
enemySpawnRate = 60;       // Lower = more enemies

// Game settings
lives = 3;                 // Starting lives
```

### 4. Change Player Ship

Find the player drawing code:

```javascript
// Current: Triangle ship
ctx.beginPath();
ctx.moveTo(player.x, player.y - player.height / 2);
ctx.lineTo(player.x - player.width / 2, player.y + player.height / 2);
ctx.lineTo(player.x + player.width / 2, player.y + player.height / 2);
ctx.closePath();
ctx.fill();
```

To change to a different shape, modify this section!

### 5. Add Power-ups

Add after the enemy collision code:

```javascript
// Example: Health power-up
if (Math.random() < 0.05) {  // 5% chance
  // Draw power-up
  ctx.fillStyle = '#22c55e';
  ctx.fillRect(enemy.x, enemy.y, 20, 20);
  
  // Check collision
  if (collision with player) {
    lives++;  // Extra life!
  }
}
```

### 6. Change Enemy Types

Find `spawnEnemy()` and add:

```javascript
function spawnEnemy() {
  const size = Math.random() * 30 + 20;
  const type = Math.random();
  
  if (type < 0.7) {
    // Normal enemy - one shot
    enemies.push({ ... });
  } else if (type < 0.9) {
    // Tank enemy - takes 3 hits
    enemies.push({ ...hp: 3, color: '#f97316'... });
  } else {
    // Fast enemy
    enemies.push({ ...speed: enemySpeed * 2, size: 15... });
  }
}
```

---

## 🤖 AI Customization Guide

### Using Claude Code

Tell Claude what you want:

```
Update my game template:
- Name: "Cosmic Wars"
- Colors: Purple (#a855f7) and cyan (#8b5cf6)
- Player speed: 10
- Enemy spawn rate: 30
- Add boss every 3 levels
```

### Using Ollama

```bash
ollama run llama3.2

# Ask:
"Generate JavaScript code to add a boss enemy that appears 
every 5 levels in my space shooter game"
```

### AI Prompt Templates

**Change everything:**
```
I have a space shooter game in a single HTML file.
Generate the JavaScript to:
1. Change player speed to 10
2. Add boss enemies every 5 levels
3. Add a shield power-up
4. Add a score multiplier power-up
```

**Add new features:**
```
Generate code to add these to my HTML game:
- Health bar
- High score saved in localStorage
- Sound effects (simple beeps)
- Different enemy types
```

---

## 🎮 Game Variables Reference

| Variable | Default | Description |
|----------|---------|-------------|
| `player.speed` | 7 | Player movement speed |
| `bulletSpeed` | 10 | How fast bullets travel |
| `enemySpeed` | 2 | Base enemy speed |
| `enemySpawnRate` | 60 | Frames between spawns |
| `lives` | 3 | Starting lives |

---

## 🌐 Hosting

### Option 1: Netlify Drop
1. Go to https://app.netlify.com/drop
2. Drag your folder
3. Share your game URL!

### Option 2: Itch.io
1. Create itch.io account
2. Upload index.html as HTML5 game
3. Add thumbnails and description

### Option 3: GitHub Pages
1. Create repo, upload files
2. Enable GitHub Pages
3. Share URL!

---

## ✅ Checklist

- [ ] Tested the game
- [ ] Changed title to your game name
- [ ] Adjusted difficulty (if wanted)
- [ ] Changed colors (if wanted)
- [ ] Deployed to web!

---

## 📁 File Structure

```
game-template/
└── index.html    ← Single file, everything included!
```

---

## 🆘 Troubleshooting

**Game runs slow?**
- Reduce number of stars
- Lower enemy spawn rate

**Controls not working?**
- Click on the game first
- Check you're using Arrow keys or WASD

**Cursor not showing?**
- Normal on touch devices

---

## 🎉 Next Steps

- Add more enemy types
- Add sound effects
- Add levels with different backgrounds
- Add boss battles
- Add multiplayer!

---

## 📝 License

MIT — Use it however you like!

---

**Made with ❤️ and AI**
