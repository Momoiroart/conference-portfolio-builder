# Manual Setup Tutorial

> Step-by-step guide to customize your portfolio without any AI tools.

## What You'll Learn

- How to edit the HTML file
- Change colors, text, images
- Add your projects and skills
- Deploy to the web

## Prerequisites

- A text editor (VS Code recommended)
- A web browser
- 15-30 minutes

---

## Step 1: Get the Template

1. Go to [conference-portfolio-builder repository](https://github.com/Momoiroart/conference-portfolio-builder)
2. Click **Code** → **Download ZIP**
3. Extract the folder
4. Open `portfolio-basic/index.html` in your text editor

---

## Step 2: Change Your Name

Find these lines in the HTML:

```html
<!-- Header logo -->
<a href="#" class="logo">Your<span>Name</span></a>

<!-- Hero title -->
<h1><span class="line gradient">Your Name</span></h1>

<!-- Footer -->
<p>© 2026 Your Name.</p>
```

Replace `Your Name` with your actual name!

---

## Step 3: Update Your Bio

Find the **About** section:

```html
<div class="about-text">
  <p>I'm a developer and designer based in [Your Location]. 
     I love creating things...</p>
  <p>My journey started when [your story]...</p>
</div>
```

Replace the placeholder text with your own bio!

---

## Step 4: Change Colors

Find `:root` at the top of the CSS:

```css
:root {
  --accent: #ff6b9d;          /* Change this pink */
  --accent-secondary: #4af0e8; /* Change this cyan */
  --bg-primary: #06060b;      /* Change background */
}
```

Try these color combinations:

| Theme | Pink | Cyan |
|-------|------|------|
| Purple | #a855f7 | #8b5cf6 |
| Orange | #f97316 | #fb923c |
| Green | #22c55e | #4ade80 |

---

## Step 5: Add Your Skills

Find the skills section:

```html
<div class="skills-grid">
  <div class="skill-card">
    <span class="skill-icon">🌐</span>
    <h3>Web Development</h3>
    <p>Building modern websites...</p>
  </div>
</div>
```

To add more skills:
1. Copy a `.skill-card` block
2. Paste it inside `.skills-grid`
3. Change the icon, title, and description

---

## Step 6: Add Your Projects

Find the projects section:

```html
<div class="project-card">
  <div class="project-image">
    <span class="project-icon">🚀</span>
  </div>
  <div class="project-info">
    <h3>Project One</h3>
    <p>Description here.</p>
    <div class="project-tags">
      <span class="tag">React</span>
    </div>
  </div>
</div>
```

To add more projects:
1. Copy the `.project-card` block
2. Paste inside `.projects-grid`
3. Update title, description, and tags

---

## Step 7: Update Contact Links

Find the contact section:

```html
<a href="mailto:your@email.com" class="contact-card">
<a href="https://github.com/yourusername" target="_blank">
<a href="https://twitter.com/yourusername" target="_blank">
```

Replace the URLs with your actual links!

---

## Step 8: Preview Your Changes

1. Save your file
2. Double-click `index.html` to open in browser
3. See your changes!
4. Go back to editor to make more changes
5. Refresh browser to see updates

---

## Step 9: Deploy to Web

### Option A: Netlify (Easiest)

1. Put `index.html` in a folder
2. Go to https://app.netlify.com/drop
3. Drag your folder onto the page
4. Get your free URL!

### Option B: GitHub Pages

1. Create a new GitHub repository
2. Upload your `index.html`
3. Go to **Settings** → **Pages**
4. Enable GitHub Pages

### Option C: Vercel

```bash
# Install Vercel
npm install -g vercel

# Deploy
vercel
```

---

## 🎉 You're Done!

Your portfolio is now live on the internet!

**Next steps:**
- Share your portfolio link
- Connect with us on social media
- Keep updating your projects!

---

## Need Help?

- Check the README.md in the template folder
- Visit our learn guide website
- Ask in our community

---

[← Back to Portfolio Builder](../README.md)
