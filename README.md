# 🌟 BrainBurst Academy – Grade 4 Learning Platform

An interactive, gamified learning web app for Grade 4 students with **full user authentication, persistent profiles, and a personal dashboard**. Built with pure HTML, CSS, and JavaScript — no frameworks, no dependencies, works in any browser.

![Grade 4](https://img.shields.io/badge/Grade-4-brightgreen) ![HTML CSS JS](https://img.shields.io/badge/Built%20with-HTML%20%7C%20CSS%20%7C%20JS-orange) ![GitHub Pages](https://img.shields.io/badge/Hosted-GitHub%20Pages-blue)

---

## 🚀 Live Demo

> 🔗 **[https://YOUR-USERNAME.github.io/brainburst-academy](https://YOUR-USERNAME.github.io/brainburst-academy)**  
> *(Replace `YOUR-USERNAME` with your GitHub username after deployment)*

---

## ✨ What's New — Auth + Dashboard Update

This version adds a complete authentication and profile system on top of the original quiz engine:

### 🔐 Authentication System
- **Create Account** — Register with first/last name, email, password, and a custom emoji avatar
- **Login** — Sign in via email or username, with encoded password storage
- **Persistent Sessions** — Stay logged in across browser refreshes via `localStorage`
- **Secure Logout** — Available from every screen via the header

### 📊 Personal Dashboard
- **Profile header** — Avatar, name, join date at a glance
- **Stat cards** — Total quizzes, average score %, total points, badges earned
- **Subject Progress** — Color-coded progress bars for all 6 subjects with best score
- **Quiz History** — Last 10 quiz results with subject, score %, correct/total, points earned, date
- **Badge showcase** — All earned badges displayed as pill tags

### 💾 localStorage Data Model
Each user profile is stored as a JSON object in `localStorage` under the key `bb_users_v2`:

```json
{
  "email": "student@example.com",
  "username": "priyasharma",
  "name": "Priya Sharma",
  "firstName": "Priya",
  "avatar": "🦋",
  "pass": "<btoa-encoded>",
  "joinedAt": "2025-01-15T10:30:00.000Z",
  "totalScore": 340,
  "badges": ["math_done", "math_ace", "eng_done"],
  "subjScores": {
    "math": 92,
    "english": 67
  },
  "quizHistory": [
    {
      "subjectId": "math",
      "subjectName": "Mathematics",
      "subjectIcon": "🔢",
      "correct": 11,
      "total": 12,
      "pct": 92,
      "pts": 115,
      "date": "2025-01-15T11:00:00.000Z"
    }
  ]
}
```

**Storage Keys Used:**
| Key | Contents |
|-----|----------|
| `bb_users_v2` | Array of all registered user objects |
| `bb_session_v2` | Currently logged-in user object |

---

## 📚 Original Features

- 🎯 **6 Subjects** — Mathematics, EVS & Science, English, Hindi, Kannada, Computers
- 📖 **Full Syllabus** — Chapter-by-chapter reading before each quiz
- 🧠 **Quiz Engine** — 12 random questions per attempt (from pool of 15)
- ⭐ **Two Difficulty Levels** — Easy (+10 pts) and Medium (+15 pts)
- 🏅 **14 Collectible Badges** — Subject badges, performance badges & legendary titles
- 🎊 **Confetti Animations** on badge earn
- 📊 **Live Score Tracking** throughout the session
- 📱 **Fully Responsive** — Works on mobile, tablet & desktop
- 🎨 **Candy Adventure Theme** — Vibrant, child-friendly design

---

## 🗂️ Project Structure

```
brainburst-academy/
│
├── index.html                  # Main HTML — all screens including auth & dashboard
├── 404.html                    # Custom 404 page
├── README.md                   # This file
├── .gitignore                  # Git ignore rules
│
└── assets/
    ├── css/
    │   └── style.css           # All styles — original + auth + dashboard
    ├── js/
    │   └── app.js              # All logic — auth, localStorage, quiz engine, dashboard
    └── images/
        └── favicon.svg         # App favicon (lion mascot)
```

---

## 🖥️ Screens & Flow

```
screen-auth  ──→  screen-welcome  ──→  screen-home
(Login/Signup)    (Hello splash)         │
                                         ├──→  screen-subject
                                         │         ├──→  screen-syllabus ──→ screen-quiz
                                         │         └──→  screen-quiz ──→ screen-result
                                         ├──→  screen-badges
                                         └──→  screen-dashboard
```

All screens share a sticky app header with the user avatar, score, navigation, and logout button.

---

## 🛠️ How to Deploy on GitHub Pages

### Step 1 — Create a GitHub Repository
1. Go to [github.com](https://github.com) and log in
2. Click **"New repository"** → Name it `brainburst-academy` → Set to **Public** → Create

### Step 2 — Upload Files
Maintain this exact folder structure when uploading:
```
index.html
404.html
README.md
.gitignore
assets/css/style.css
assets/js/app.js
assets/images/favicon.svg
```

**Option A — GitHub website drag & drop:**
1. Click "uploading an existing file" on the repo page
2. Drag all files preserving the folder structure
3. Click "Commit changes"

**Option B — Git CLI:**
```bash
git init
git add .
git commit -m "🚀 BrainBurst Academy with Auth + Dashboard"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/brainburst-academy.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages
1. Repo → **Settings** → **Pages**
2. Source: **Deploy from a branch** → Branch: `main`, Folder: `/ (root)`
3. Click **Save** → Wait 1–2 min → Visit `https://YOUR-USERNAME.github.io/brainburst-academy`

---

## 🌐 External Dependencies (CDN only)

```
https://fonts.googleapis.com/css2?family=Fredoka+One&family=Nunito:wght@400;600;700;800;900
```

No frameworks. No npm. No build step. Just open `index.html`.

---

## 🧩 Tech Stack

| Technology | Usage |
|---|---|
| HTML5 | All app screens, auth forms, dashboard layout |
| CSS3 | Animations, gradients, responsive layouts, auth & dashboard styles |
| Vanilla JS (ES6) | Auth logic, localStorage CRUD, quiz engine, scoring, badge logic, dashboard rendering |
| localStorage | User accounts, sessions, quiz history, badges, scores |
| Google Fonts | Fredoka One + Nunito |
| CSS Grid & Flexbox | All layouts |

---

## 📱 Browser Support

| Browser | Support |
|---|---|
| Chrome / Edge | ✅ Full |
| Firefox | ✅ Full |
| Safari (iOS & macOS) | ✅ Full |
| Samsung Internet | ✅ Full |

---

## 🔒 Security Note

Passwords are stored using `btoa()` (Base64 encoding) which is **not cryptographic encryption**. This is appropriate for a school learning app where the goal is session management, not high-security authentication. For a production system, server-side password hashing (bcrypt, argon2) would be required.

---

*Made with ❤️ for Grade 4 learners everywhere 🦁*
