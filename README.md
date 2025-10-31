# 🏥 Mobile Health App

A full-stack healthcare management system that connects patients and doctors.  
Patients can manage medical profiles & appointments, while doctors can review patient history, approve consultations, and issue prescriptions.

---

## ✨ Features
- Patient sign-in, medical profile, appointment booking
- Doctor dashboard with appointment approval & completion
- Medical history & prescription management
- MongoDB cloud database support
- Role-based authentication (Patient / Doctor)

---

## 🛠️ Tech Stack
| Layer | Technology |
|------|------------|
| Frontend | React + Vite + TypeScript + TailwindCSS |
| Backend | Node.js + Express |
| Database | MongoDB Atlas |
| Mobile Runtime | Capacitor + Android Studio (for emulator or real device) |

---

# 🚀 Project Setup

## 1️⃣ Clone Repository
```bash
git clone https://github.com/<mistreatedbee>/<HealthApp>.git
cd <your-repo>
````

---

# 🔧 Backend Setup

```bash
cd backend
npm install
```

Run backend:

```bash
npm run dev
```

Backend runs at:

```
http://localhost:5000
```

---

# 🎨 Frontend Setup

```bash
cd ../frontend
npm install
```

Create `.env` in frontend:

```
VITE_API_URL=http://localhost:5000
```

Run frontend:

```bash
npm run dev
```

Frontend runs at:

```
http://localhost:5173
```

---

# 📱 Run as a Full Mobile App (Using Capacitor)

This allows the project to run as a real Android app inside **Android Studio**.

### 1. Install Capacitor in the frontend project

```bash
cd frontend
npm install @capacitor/core @capacitor/cli
```

### 2. Initialize Capacitor

```bash
npx cap init
```

| Question | Example Answer            |
| -------- | ------------------------- |
| App Name | MobileHealth              |
| App ID   | com.mobilehealth |

### 3. Add Android Platform

```bash
npm install @capacitor/android
npx cap add android
```

### 4. Build Frontend

```bash
npm run build
```

### 5. Sync Build to Capacitor Project

```bash
npx cap sync
```

### 6. Open Android Studio

```bash
npx cap open android
```

### 7. Run on Android Emulator

Click **Run ▶️** in Android Studio.

---

## 🔗 If Your Backend is Local (Emulator Cannot Use localhost)

Use this instead of localhost:

```
VITE_API_URL=http://10.0.2.2:5000
```

Then rebuild & sync again:

```bash
npm run build
npx cap sync
```

> `10.0.2.2` = special IP that lets the Android emulator reach your computer.

---

# 🌍 Deployment (When Ready)

| Part     | Host             | Notes                                |
| -------- | ---------------- | ------------------------------------ |
| Frontend | Vercel / Netlify | `npm run build`, then deploy `dist/` |
| Backend  | Render / Railway | Must keep server running             |
| Database | MongoDB Atlas    | Already production-ready ✅           |

After deploying backend, update **frontend `.env`:**

```
VITE_API_URL=https://your-backend-url.com
```

Rebuild & redeploy frontend:

```bash
npm run build
```

---

# 🆘 Troubleshooting

| Issue                                 | Fix                                             |
| ------------------------------------- | ----------------------------------------------- |
| Emulator cannot reach backend         | Use `http://10.0.2.2:5000` instead of localhost |
| MongoDB connection fails              | Add your IP in MongoDB Atlas → Network Access   |
| Doctor Dashboard missing medical info | Ensure backend `/patients/:id` route is active  |

---
