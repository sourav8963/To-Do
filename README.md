# 📅 Daily Focus — To-Do Web App

A clean, interactive single-page to-do app with a **daily streak tracker**, a **main goal**, and **other goals**. Built with pure HTML, CSS, and JavaScript — no dependencies, no build step.

---

## ✨ Features

- 🔥 **Daily Streak Counter** — tracks consecutive days where at least one goal was completed
- 📅 **7-Day Dot Calendar** — visual history of the past week's activity
- 🎯 **Main Goal** — highlight your single most important task for the day
- ✅ **Other Goals** — add, complete, edit, and delete additional daily tasks
- 📊 **Progress Bar** — shows % of today's goals completed
- 💾 **Persistent Storage** — all data saved to `localStorage`, survives page refreshes and browser restarts
- 🎉 **Confetti Burst** — satisfying animation when you complete a goal
- 🍞 **Toast Notifications** — subtle feedback on actions

---

## 🚀 Getting Started

No installation or build process needed.

```bash
# Clone the repo
git clone https://github.com/your-username/daily-focus.git
cd daily-focus

# Open in your browser
open index.html
```

Or simply **double-click `index.html`** to open it in your default browser.

---

## 🗂 File Structure

```
daily-focus/
└── index.html   # The entire app — HTML, CSS, and JS in one file
```

---

## 🧠 How It Works

### Storage
All data is saved to `localStorage` under the key `dailyfocus_v2`. Each day gets its own entry keyed by ISO date (`YYYY-MM-DD`):

```json
{
  "2025-03-23": {
    "mainGoal": "Finish the project proposal",
    "mainDone": true,
    "goals": [
      { "text": "Reply to emails", "done": true },
      { "text": "Go for a run", "done": false }
    ]
  }
}
```

### Streak Logic
The streak increments for every consecutive past day (including today) where either:
- The **main goal** was marked complete, OR
- **At least one other goal** was marked complete

### Progress Bar
Progress = `(completed goals) / (total goals)` × 100, where total includes the main goal + all other goals.

---

## 🎨 Design

- **Font:** Playfair Display (headings) + DM Mono (body)
- **Theme:** Dark with warm gold and amber accents
- **Background:** Subtle grain texture overlay for depth

---

## 🛠 Customization

All design tokens are CSS variables at the top of the `<style>` block:

```css
:root {
  --bg: #0e0e0f;
  --accent: #f0c060;   /* Gold — streak, progress */
  --accent2: #e07050;  /* Amber — today dot, gradient end */
  --done: #4a9a6a;     /* Green — completed goals */
}
```

Change these to restyle the entire app instantly.

---

## 📦 Dependencies

None. The app uses:
- [Google Fonts](https://fonts.google.com/) — loaded via CDN (requires internet on first load; cached after)
- Native browser `localStorage` API

---

## 📄 License

MIT — free to use, modify, and distribute.
