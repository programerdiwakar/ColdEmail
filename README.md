# AI Cold Email Generator (MERN Stack + Groq AI API)

An end-to-end full-stack AI Cold Email Generator built with the MERN stack (MongoDB, Express.js, React, Node.js) and integrated with the Groq AI API (utilising models like Llama 3) [1, 3, 7, 8]. The application enables job seekers and outreach professionals to generate tailored cold outreach packages—including email subject lines, body copy, LinkedIn DMs, and follow-up sequences—based on custom user prompts [3, 4, 106, 116].

---

## 🌟 Features

- **AI-Powered Outreach Generation:** Uses Groq AI API to generate subject lines, cold email bodies, LinkedIn DMs, and follow-up emails in a single request [3, 4, 106, 116].
- **User Authentication & Authorization:** Secure registration and login using JSON Web Tokens (JWT) and Bcrypt password hashing [3, 5, 26, 81].
- **OTP Email Verification:** Automated One-Time Password (OTP) verification system powered by NodeMailer and Gmail SMTP with 10-minute expiration [3, 10, 38, 45, 50].
- **Persistent Email History:** Logged search history in MongoDB storing user prompts, generated email content, and timestamps for retrieval [5, 10, 105, 107, 118, 126].
- **Protected Middleware:** Custom JWT-based route middleware to restrict AI generation and history endpoints to authenticated users [9, 94, 95, 98].
- **Monorepo Architecture:** Single repository structure running client (React + Vite) and server (Node + Express) concurrently using `concurrently` [1, 7, 180].

---

## 🛠️ Tech Stack

### **Frontend**
- **Framework:** React.js (Vite) [6, 9]
- **Styling:** Tailwind CSS [2, 8]
- **Icons & Notifications:** HeroIcons [138], React Hot Toast [138]
- **HTTP Client:** Axios [8, 138]
- **Routing:** React Router DOM [138]

### **Backend**
- **Runtime:** Node.js & Express.js [8, 21]
- **Database:** MongoDB & Mongoose [8, 27, 36]
- **Authentication:** JWT (`jsonwebtoken`), Bcrypt (`bcryptjs`) [26, 27, 82]
- **Email Service:** NodeMailer (Gmail SMTP) [10, 27, 50]
- **Environment Management:** Dotenv & CORS [26]

### **AI Services**
- **API Provider:** Groq AI API (Groq Cloud) [3, 5, 100, 102]
- **Models:** Llama 3 / Llama 3.3 Versatile [3, 110]

---

## 📁 Project Structure

```
├── client/                 # React (Vite) Frontend [6]
├── server/                 # Node.js / Express Backend [6, 21]
│   ├── config/             # Database Connection Configuration [28, 54]
│   ├── controllers/        # Auth & AI Route Controllers [28, 32, 104]
│   ├── middlewares/        # Custom JWT Auth Middleware [28, 94, 95]
│   ├── models/             # Mongoose Schemas (User, EmailHistory) [28, 36, 105]
│   ├── routes/             # Auth & AI API Routes [28, 29, 94]
│   └── utils/              # NodeMailer Email Helper [28, 48, 50]
├── package.json            # Monorepo Scripts & Concurrently Config [175, 180]
└── README.md
```

---

## ⚙️ Environment Variables

Create a `.env` file in the `server` directory based on `.env.example`:

```env
PORT=3000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
EMAIL_USER=your_gmail_address
EMAIL_PASS=your_gmail_app_password
GROQ_API_KEY=your_groq_api_key
```
*(Reference: [24, 51, 53, 59, 85, 112])*

---

## 📦 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/ai-cold-email-generator.git
   cd ai-cold-email-generator
   ```
   *(Reference: [12])*

2. **Install all dependencies across root, client, and server:**
   ```bash
   npm run install-all
   ```
   *(Reference: [180, 199])*

3. **Run the application in development mode:**
   ```bash
   npm run dev
   ```
   *(Reference: [1, 180, 199])*
   
   *This command leverages `concurrently` to start both the Express server and the Vite React frontend simultaneously [1, 148, 180, 199].*

---

## ☁️ Deployment

The application is configured for unified monorepo deployment on **Render**:
1. Configure static file serving from `client/dist` in the Express server [196].
2. Set Environment Variables on the Render dashboard [60, 112].
3. Set build and start commands:
   - **Install Command:** `npm run install-all` [180, 202]
   - **Build Command:** `npm run build` [196, 202]
   - **Start Command:** `npm run start` [180, 202]

*(Reference: [2, 13, 196, 202])*
