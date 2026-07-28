# 🕯️ WhisperWall — Public Confession App

A beautiful, dark-themed public confession website with **login + OTP verification**.

---
<div align="center">

<!-- Animated Header -->

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:111827,100:7c3aed&height=200&section=header&text=WhisperWall&fontSize=55&fontColor=ffffff&animation=fadeIn&fontAlignY=35" />

<h3>✨ A beautiful, dark-themed public confession website with OTP login verification</h3>

<p> <a href="https://github.com/Ronit049/-WhisperWall"> <img src="https://img.shields.io/github/stars/Ronit049/-WhisperWall?style=for-the-badge&color=7c3aed" alt="Stars" /> </a> <a href="https://github.com/Ronit049/-WhisperWall/forks"> <img src="https://img.shields.io/github/forks/Ronit049/-WhisperWall?style=for-the-badge&color=8b5cf6" alt="Forks" /> </a> <a href="https://github.com/Ronit049/-WhisperWall/blob/main/LICENSE"> <img src="https://img.shields.io/github/license/Ronit049/-WhisperWall?style=for-the-badge&color=ec4899" alt="License" /> </a> </p>

<p> <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=22&pause=1000&color=E9D5FF&center=true&vCenter=true&width=850&lines=Confess+freely.;Share+anonymously.;Explore+the+wall.;Built+with+HTML%2C+CSS+%26+JavaScript." alt="Typing SVG" /> </p>

<p> <a href="https://whisper-wall-blue.vercel.app/"> <img src="https://img.shields.io/badge/Live%20Demo-Visit%20Now-22c55e?style=for-the-badge&logo=vercel&logoColor=white" alt="Live Demo" /> </a> <a href="https://github.com/Ronit049/-WhisperWall"> <img src="https://img.shields.io/badge/View%20Code-GitHub-111827?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /> </a> </p>

</div>
## 📁 File Structure

```
confession-app/
│
├── index.html          ← Login page (Step 1: Name & Email → Step 2: OTP → Step 3: Success)
├── wall.html           ← Main confession wall (protected, requires login)
│
├── css/
│   ├── style.css       ← Global shared styles (CSS variables, buttons, toast, fields, background)
│   ├── login.css       ← Login page specific styles (card, OTP boxes, steps, animations)
│   └── wall.css        ← Wall page specific styles (header, hero, cards, feed, lightbox)
│
├── js/
│   ├── auth.js         ← Authentication logic (OTP generation, verification, countdown, session)
│   └── wall.js         ← Wall logic (post, like, share, filter, search, sort, lightbox)
│
└── README.md           ← This file
```

---

## ✨ Features

### 🔐 Login Flow (index.html)
- **Step 1** — Enter your name & email
- **Step 2** — 6-digit OTP verification with auto-advance, paste support, 60s resend countdown
- **Step 3** — Welcome screen → redirect to wall
- Session stored in `localStorage` (persists across page refreshes)
- Auth guard: wall page redirects to login if not verified

### 🕯️ Confession Wall (wall.html)
- Post confessions with an optional title and mood emoji
- 1000 character limit with live counter
- Cards in a responsive masonry-style grid
- Click any card to open a **lightbox** with full text
- **Like** confessions (one like per user)
- **Share** (Web Share API or clipboard fallback)
- **Search** by title or content
- **Sort** by: Newest, Oldest, Most Liked
- Logout button clears session

---

## 🚀 How to Run

Simply open `index.html` in any modern browser — no build tools needed.

> **Demo OTP:** Since there's no backend, the OTP is logged to the browser DevTools Console.
> Open DevTools → Console to see the OTP after clicking "Send OTP".

---

## 🔧 Adding a Real Backend (Production)

To make OTP real, replace the mock in `js/auth.js` → `sendOTP()`:

```javascript
// Replace this:
generatedOTP = Math.floor(100000 + Math.random() * 900000).toString();
console.log(`[DEV] OTP for ${email}: ${generatedOTP}`);

// With a fetch to your backend:
const res = await fetch('/api/send-otp', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email, name })
});
// Backend generates OTP, emails it via SendGrid/Nodemailer, stores hash server-side
```

Then verify server-side instead of client-side.

---
## 📸 Application Screenshots

<div align="center">

### 📝 Confession Page
<img src="wishper wall confession.png" alt="WhisperWall Confession Page" width="900"/>

<br><br>

### 🎨 Frontend Interface
<img src="wishper wall frontend.png" alt="WhisperWall Frontend" width="900"/>

<br><br>

### 🔐 Login Page
<img src="wishper wall login page.png" alt="WhisperWall Login Page" width="900"/>

</div>

## 🛠️ Tech Stack

| Layer      | Tech                    |
|------------|-------------------------|
| Markup     | Pure HTML5              |
| Styling    | CSS3 (custom variables) |
| Logic      | Vanilla JavaScript (ES6+)|
| Fonts      | Google Fonts (Playfair Display + DM Sans) |
| Storage    | localStorage (client-side) |
| No dependencies | ✅ Zero npm, zero build |



---

<div align="center">

# ⭐ Support the Project

If you found this project useful, informative, or inspiring, please consider giving it a ⭐ on GitHub.

Your support helps improve the project, motivates future development, and makes it easier for others to discover it.

<a href="https://github.com/Ronit049/-WhisperWall">
  <img src="https://img.shields.io/github/stars/Ronit049/-WhisperWall?style=for-the-badge&logo=github&color=yellow" alt="GitHub Stars"/>
</a>

<br><br>

# 👨‍💻 Author

### **Ronit Raj**

<p>
Passionate Computer Science Student focused on building practical AI-powered applications,
modern web experiences, and open-source projects.
</p>

<p>
<a href="https://github.com/Ronit049">
<img src="https://img.shields.io/badge/GitHub-Ronit049-181717?style=for-the-badge&logo=github">
</a>

<a href="https://www.linkedin.com/in/YOUR-LINKEDIN">
<img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin">
</a>

<a href="mailto:YOUR_EMAIL">
<img src="https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail">
</a>

</p>

---

# 🌟 Show Your Support

If this repository helped you:

⭐ Star the repository

🍴 Fork it

🐛 Report bugs

💡 Suggest new features

🤝 Contribute to make it even better

Every contribution—big or small—is greatly appreciated.

---

# 💙 Thank You

Thank you for visiting this repository!

I truly appreciate your time and interest in this project. I hope it helps you learn something new or solve a real problem.

If you have ideas, feedback, or would like to collaborate on future projects, feel free to reach out. Contributions, discussions, and suggestions are always welcome.

**Happy Coding! 🚀**

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=7C3AED&center=true&vCenter=true&width=500&lines=Thanks+for+Visiting!;Happy+Coding!;Keep+Building+Amazing+Things!;See+You+Again!+👋" />

<br>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:7C3AED,100:111827&height=160&section=footer"/>

</div>
