# 🕯️ WhisperWall — Public Confession App

A beautiful, dark-themed public confession website with **login + OTP verification**.

---

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

## 🛠️ Tech Stack

| Layer      | Tech                    |
|------------|-------------------------|
| Markup     | Pure HTML5              |
| Styling    | CSS3 (custom variables) |
| Logic      | Vanilla JavaScript (ES6+)|
| Fonts      | Google Fonts (Playfair Display + DM Sans) |
| Storage    | localStorage (client-side) |
| No dependencies | ✅ Zero npm, zero build |



## Author

**Ronit Raj**
feel free to Connect 💗  
[🏆 CodeChef](https://www.codechef.com/users/its_rsr04)

[💡 HackerRank](https://www.hackerrank.com/profile/ronitrajrsr0409)
---

## Show Your Support

If you found this project useful, please consider giving it a ⭐ on GitHub.

Your support motivates me to build more projects and improve my skills.

---

## Thank You
