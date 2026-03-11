# DREX COACH AI 🔴

**Performance Coaching Platform — by Drexler**

AI-powered fitness coaching app. Adapts workouts and nutrition to your daily mood, energy, and hormonal cycle. Built for real clients, managed by a single coach.

---

## 🚀 Quick Deploy

### Frontend (Netlify) — single file, zero config

1. Go to [netlify.com](https://netlify.com) and log in
2. Click **"Add new site" → "Deploy manually"**
3. Drag and drop the `frontend/` folder (or just `index.html`) into the drop zone
4. Your site is live instantly — no build step needed
5. Update the `API` constant at the top of `index.html` with your Railway backend URL:

```js
const API = 'https://your-railway-backend.up.railway.app/api';
```

### Backend (Railway)

1. Go to [railway.app](https://railway.app) and create a new project
2. Add a **MySQL** service and copy the connection variables
3. Deploy the `/backend` folder via GitHub or CLI
4. Set environment variables (copy from `.env.example`):

```
DB_HOST=         # MySQL host (Railway internal)
DB_PORT=3306
DB_USER=         # MySQL user
DB_PASS=         # MySQL password
DB_NAME=drexcoach
JWT_SECRET=      # Any long random string
ANTHROPIC_API_KEY=  # Your Claude API key
TRAINER_EMAIL=drexler@drexcoach.com
TRAINER_PASS=drex2025admin!
```

---

## 🧪 Test Accounts

### Client Account
- **Email:** alex18alvarez@gmail.com
- **Password:** Valentina1505
- **Role:** client (Pro plan active)

### Trainer / Admin Account (temporary — pre-Supabase)
- **Email:** drex@admin.com
- **Password:** drex1234
- **Role:** trainer
- Or click the logo **5 times fast** for instant admin access

> ⚠️ These credentials are hardcoded for local testing only. They will be removed in Etapa 2 when Supabase Auth is integrated.

---

## ✅ Etapa 1 — Completed Features

### Client Side
- 🔐 Register / Login / Forgot password / Reset password
- 📊 Dashboard with calorie chart, weekly activity strip, KPI cards
- 🧠 Daily mood & energy check-in (affects workout volume automatically)
- 🏋️ Training page — shows today's exercises from coach's assigned routine
  - Rest days shown automatically based on coach's schedule config
  - AI adapts volume up/down based on mood + energy
- 🍽️ Nutrition — photo upload → AI auto-analyzes → saves to diary instantly
  - Extracts: food name, kcal, protein, carbs, fat, fitness recommendation
- 💬 AI Chat (Claude Sonnet) — personalized by profile, mood, and food log
- 📸 Food photo analysis in chat
- 🌙 Female hormonal cycle tracking — adapts AI and training by phase
- 📋 Subscription wall (Stripe payment links — pending real URLs)
- ⚠️ Profile completion banner — prompts client to fill missing data
- ⚙️ Settings — profile, password change, referral code

### Admin Panel (Trainer)
- 👥 Client list with search, KPI row (total clients, active subs, revenue)
- 🧑‍💼 Per-client detail: custom AI prompt, private notes, quick-prompt chips
- 📋 Routine Builder — create named routines, assign exercises per day (Mon–Sun), mark active vs rest days
- 📲 WhatsApp 5AM config — coach writes base message, AI personalizes per client on send
- 🎥 Exercise library — upload exercises with muscle group and instructions
- ⚙️ AI Config — global prompt, tone, language, restrictions

---

## 🗺️ Roadmap

### Etapa 2 — Supabase + Real Auth
- [ ] Supabase Auth replacing hardcoded admin credentials
- [ ] Role-based access (trainer vs client) from database
- [ ] Stripe webhook → auto-activate subscription on payment
- [ ] Resend email integration: welcome email + 3-day expiry reminder
- [ ] Real cron job for WhatsApp 5AM delivery (via Twilio or WhatsApp Business API)
- [ ] Routine assignments stored in Supabase per client

### Etapa 3 — AI Enhancements
- [ ] Gemini 1.5 Flash for food photo analysis (faster, cheaper)
- [ ] AI-generated daily routine delivery at 5AM
- [ ] Progress tracking with body metrics charts
- [ ] Weekly AI report emailed to client

---

## 🛠️ Stack

| Layer | Technology |
|---|---|
| Frontend | HTML / CSS / JS (single file) |
| Backend | Node.js + Express + MySQL (mysql2) |
| AI | Anthropic Claude Sonnet (chat + food analysis) |
| Hosting — Frontend | Netlify |
| Hosting — Backend | Railway |
| Auth (Etapa 2) | Supabase |
| Payments | Stripe |
| Email (Etapa 2) | Resend |
| WhatsApp (Etapa 2) | Twilio / WhatsApp Business API |

---

## 📁 Project Structure

```
drexcoach_v2/
├── backend/
│   ├── server.js
│   ├── .env.example
│   └── package.json
└── frontend/
    └── index.html       ← entire frontend in one file
```

---

## 🔑 Environment Variables Reference

```env
# Database (Railway MySQL)
DB_HOST=mysql.railway.internal
DB_PORT=3306
DB_USER=root
DB_PASS=your_password
DB_NAME=drexcoach

# Auth
JWT_SECRET=your_long_random_secret_here

# AI
ANTHROPIC_API_KEY=sk-ant-...

# Trainer auto-created on first start
TRAINER_EMAIL=drexler@drexcoach.com
TRAINER_PASS=drex2025admin!
```

---

## 📬 Contact

Built by **Alexander Alvarez** — Mr. Coinsage LLC  
For **Drexler** — Performance Coach
