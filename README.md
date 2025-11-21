# ☕ MonRan Coffee House – Digital Coffee Ordering System

A full-featured MERN app for remote workers in Kinoo to order artisanal coffee online — with real-time staff order management.

![MonRan UI](./screenshots/app-screenshot.png)

---

## 🌐 Live Applications

- **Frontend (Netlify)**: [https://monran-coffee-house.netlify.app](https://monran-coffee-house.netlify.app)  
- **Backend API (Render)**: [https://mern-monran.onrender.com](https://mern-monran.onrender.com)

> ✅ Fully live, HTTPS-enabled, and publicly accessible.

---

## 🛠️ Tech Stack

- **Frontend**: React (Vite), React Router, Axios
- **Backend**: Node.js, Express, MongoDB (Mongoose)
- **Authentication**: JWT (JSON Web Tokens)
- **Database**: MongoDB Atlas
- **Hosting**: 
  - Frontend → **Netlify**
  - Backend → **Render**
- **CI/CD**: GitHub Actions
- **Styling**: Custom CSS with MonRan brand colors (`#6F4E37` coffee brown, `#E6C588` cream)

---

## 🚀 Deployment Instructions

### Backend (Render)
1. Push code to `main` branch
2. In [Render Dashboard](https://render.com):
   - Create **New → Web Service**
   - Connect `https://github.com/Hesbonrandy/mern-MonRan.git`
   - Build command: `npm install`
   - Start command: `npm start`
   - Set environment variables:
     - `MONGO_URI`: MongoDB Atlas connection string
     - `JWT_SECRET`: Strong secret (e.g., 32+ random chars)
   - Health check path: `/api/health`

### Frontend (Netlify)
1. Import repo into [Netlify](https://app.netlify.com)
2. Set:
   - **Build command**: `npm run build`
   - **Publish directory**: `frontend/dist`
3. Add environment variable:
   - Key: `VITE_API_URL`
   - Value: `https://mern-monran.onrender.com`

> 🔒 Vite only exposes variables prefixed with `VITE_`.

---

## 🔁 CI/CD Pipeline (GitHub Actions)

Automated on every `push` or `pull_request` to `main`:

- Installs backend dependencies
- Builds Vite frontend (`vite build`)
- Validates deployability

### 🖼️ CI Pipeline in Action

![CI Success](./screenshots/ci-pipeline.png)

> 💡 To capture:  
> 1. Go to your repo → **Actions** tab  
> 2. Run a workflow  
> 3. Screenshot the green success → save as `screenshots/ci-pipeline.png`

---

## 📊 Monitoring Setup

### Built-in Monitoring
- **Health Check Endpoint**:  
  `GET https://mern-monran.onrender.com/api/health`  
  Returns:
  ```json
  { "status": "OK", "uptime": 1234.5 }