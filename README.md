<div align="center">

# 🌐 AI Web Builder
### AI-Powered Website Generator

![Made with Node.js](https://img.shields.io/badge/Backend-Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express.js](https://img.shields.io/badge/Framework-Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![HTML CSS JS](https://img.shields.io/badge/Frontend-HTML%20CSS%20JS-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Gemini API](https://img.shields.io/badge/AI-Google%20Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)

**Generate complete, responsive websites from a single text prompt — instantly.**

[🚀 View Demo](#how-to-use) • [📦 Installation](#getting-started) • [📸 Screenshots](#screenshots) • [👩‍💻 Author](#author)

</div>

---

## 📌 About the Project

**AI Web Builder** lets users create full website layouts using natural language. Just describe the website you want — the AI generates structured HTML, CSS, and JavaScript in real time, which you can preview, save, and download instantly.

No design skills needed. No manual coding from scratch. Just type and generate. ✨

> Built for students, developers, and beginners who want to rapidly prototype landing pages, UI designs, and website layouts using AI.

---

## ✨ Features

- 🧠 **AI-Powered Generation** — Describe your website, get full frontend code instantly
- 👁️ **Live Preview** — See your generated website inside an iframe in real time
- 💾 **Save History** — All generated pages saved to MySQL for future reference
- 📥 **Download Code** — Export generated HTML/CSS/JS with one click
- 🔐 **User Auth** — Signup & login system with secure sessions
- 🔄 **AI Fallback Support** — Uses Gemini → Groq → OpenRouter as backup providers
- 📱 **Responsive UI** — Clean, interactive interface that works on all screen sizes

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | HTML, CSS, JavaScript |
| Backend | Node.js, Express.js |
| Database | MySQL |
| AI Services | Google Gemini API, Groq API, OpenRouter API |
| API Communication | REST APIs |
| Tools | VS Code, Git, npm |

---

## 📁 Project Structure

```
web-builder2/
├── BACKEND/
│   ├── DB/
│   ├── Aifallback.js       # Fallback AI provider logic
│   ├── db.js               # MySQL connection
│   ├── server.js           # Main Express server
│   ├── .env                # API keys (not pushed to GitHub)
│   └── package.json
│
├── FRONTEND/
│   ├── index.html          # Main UI
│   ├── script.js           # Frontend logic & API calls
│   └── style.css           # Styling
│
├── backend-error.log
└── frontend-live.log
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have installed:
- [Node.js](https://nodejs.org/) (v14+)
- [MySQL Server](https://dev.mysql.com/downloads/)
- A valid [Google Gemini API Key](https://makersuite.google.com/app/apikey)

---

### 🔧 Backend Setup

```bash
# 1. Clone the repository
git clone https://github.com/DharmaShree04/AI-WebBuilder.git

# 2. Go to backend folder
cd web-builder2/BACKEND

# 3. Install dependencies
npm install
```

**Set up MySQL database:**
```sql
CREATE DATABASE ai_builder;
```
> The backend auto-creates the `users` and `generated_pages` tables on first run.

**Update database credentials in `db.js`:**
```js
const db = mysql.createConnection({
  host: 'localhost',
  user: 'root',
  password: 'your_mysql_password',
  database: 'ai_builder'
});
```

**Create a `.env` file inside `/BACKEND`:**
```env
PORT=5000
GEMINI_API_KEY=your_gemini_api_key_here
GROQ_API_KEY=your_groq_api_key_here
OPENROUTER_API_KEY=your_openrouter_api_key_here
```

> ⚠️ Never push your `.env` file to GitHub!

**Start the backend:**
```bash
npm start
```

✅ Backend runs at: `http://localhost:5000`

Test it:
```
http://localhost:5000/health
```
Expected response:
```json
{
  "status": "ok",
  "service": "ai-frontend-builder-backend"
}
```

---

### 🎨 Frontend Setup

The frontend is plain HTML/CSS/JS — no build step needed!

**Recommended: Use Live Server in VS Code**
1. Open project in VS Code
2. Right-click `FRONTEND/index.html`
3. Click **"Open with Live Server"**

> Make sure backend is running on port `5000` before opening the frontend.

---

## 🔌 REST API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Backend status message |
| GET | `/health` | Check if backend is running |
| POST | `/signup` | Register a new user |
| POST | `/login` | Login existing user |
| POST | `/generate-ai` | Generate website code using AI |
| GET | `/history` | Fetch all generated websites |
| GET | `/history/:id` | Fetch a specific generated website |

---

## 🎯 How to Use

1. Start MySQL server
2. Start backend:
```bash
cd BACKEND && npm start
```
3. Open `FRONTEND/index.html` with Live Server
4. Sign up or log in
5. Enter a prompt like:
```
Create a modern landing page for a fitness app with pricing,
features, testimonials, and a call-to-action section.
```
6. Click **Generate** ✨
7. Preview → Save → Download your code!

---

## 💡 Example Prompts

```
Build a modern SaaS landing page for a finance dashboard
with pricing, testimonials, feature cards, and an ROI calculator.
```
```
Create a portfolio website for a UI/UX designer with
a hero section, projects grid, skills, and contact form.
```
```
Generate an e-commerce homepage for a sneaker brand
with featured products, banner, and newsletter signup.
```

---

## 📸 Screenshots

**Home Page:**

<img width="1360" alt="Home Page" src="https://github.com/user-attachments/assets/e3cb769e-1294-4700-90aa-bba30e9e3729" />

**Generated Output:**

<img width="955" alt="Generated Result" src="https://github.com/user-attachments/assets/3a1d5ee6-6324-40d2-ae48-df94713d890f" />

---

## 📦 Dependencies

```json
{
  "@google/generative-ai": "^0.24.1",
  "axios": "^1.14.0",
  "body-parser": "^2.2.2",
  "cors": "^2.8.6",
  "dotenv": "^17.4.0",
  "express": "^5.2.1",
  "mysql2": "^3.20.0"
}
```

---

## 🔮 Future Enhancements

- [ ] Add React.js frontend for better UI
- [ ] Deploy backend on Render / Railway
- [ ] Add drag-and-drop editor for generated pages
- [ ] Support multi-page website generation
- [ ] Add template library for quick starts
- [ ] Dark mode toggle

---

## 👩‍💻 Author

<div align="center">

**Dharmashree S**

[![Email](https://img.shields.io/badge/Email-dharmashree.s04@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:dharmashree.s04@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-DharmaShree04-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/DharmaShree04/AI-WebBuilder)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-dharmashree--s-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/dharmashree-s-)

</div>

---

## 📄 License

This project is open-source and available for learning and development purposes.

---

<div align="center">

⭐ **If you found this project useful, please give it a star!** ⭐

*Built with 💙 by Dharmashree S*

</div>
