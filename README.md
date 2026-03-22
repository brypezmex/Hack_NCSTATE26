# NoirMore

**Hack_NCState Spring 2026 project**

> NoirMore is a detective-themed fact verification system that helps users investigate claims and statements found online. Enter any claim, and our system analyzes multiple trusted sources to deliver a verdict with confidence levels and supporting evidence.

---

## 🚀 About

This repository contains the code for our submission to **Hack_NCState 2026**, North Carolina State University's premier 24-hour hackathon. Hack_NCState is a collaborative event where participants build apps, hardware, or full-stack products from scratch in just one day.

**Project Name:** NoirMore  
**Teamates:** Mykie Xiong, Gavin Leano, Bryan Perez
**Team Name:** IonEvenKnow  
**Track:** Siren's Call (AI Ethics & Safety)

To learn more about our project: [Devpost](https://devpost.com/software/noirmore?ref_content=user-portfolio&ref_feature=in_progress)
---

## 🧠 Problem Statement

In an era of rampant misinformation and deceptive AI-generated content flooding social media, we recognized an urgent need for accessible fact-checking tools. The challenge of distinguishing truth from fiction in our digital landscape inspired us to create NoirMore—a detective-themed fact verification system that empowers users to investigate claims with confidence. Our ambition to tackle this critical problem in the AI Ethics & Safety track drove us to build a practical solution that anyone can use.

---

## 💡 Solution

NoirMore aggregates and analyzes information from multiple trusted sources to deliver fact-checking results in a clear, digestible format.

- **Multi-source verification** — Queries Wikipedia, news outlets (Reuters, AP, BBC, NPR), Google Scholar, and web search to gather evidence
- **Smart analysis** — Uses pattern matching on claim-relevant content to determine supporting, contradicting, and neutral stances
- **Detective-themed UI** — Casefile-style reports with verdicts (LIKELY_TRUE, LIKELY_FALSE, DISPUTED), confidence levels, and categorized sources
- **Trust scoring** — Prioritizes reputable domains and academic sources for higher reliability

---

## 💻 Technologies Used

| Frontend | Backend | Tools |
|----------|---------|-------|
| React 19 / Vite 7 | Python / Flask | BeautifulSoup, requests |
| CSS3 | flask-cors | GitHub |

---

## 📦 Project Structure

```
Hack_NCSTATE26/
│
├── README.md
├── .gitignore
│
├── backend/
│   ├── app.py              # Flask API, FactChecker class, /submit & /api/verify endpoints
│   ├── install.py
│   ├── requirements.txt
│   └── ...
│
├── frontend/
│   ├── package.json
│   ├── vite.config.js      # Proxies /submit to backend
│   ├── index.html
│   │
│   └── src/
│       ├── assets/
│       │   ├── about.png
│       │   ├── logo.png
│       │   ├── magnifiying.png
│       │   └── sidewalk.jpeg
│       │
│       ├── components/
│       │   ├── main.jsx
│       │   ├── UrbanNoirBackground.jsx   # Main app, input, report display, about modal
│       │   ├── Report.jsx                # Casefile verdict & source counts
│       │   └── Source.jsx                # Individual source card
│       │
│       └── css/
│           ├── About.css
│           ├── Report.css
│           ├── UrbanNoirBackground.css
│           ├── Source.css
│           └── index.css
```

---

## 🔧 Setup & Installation

### Prerequisites

- **Node.js** (v18+ recommended) and **npm**
- **Python** (3.8+)
- **pip**

### 1. Clone the repository

```sh
git clone https://github.com/brypezmex/Hack_NCSTATE26.git
cd Hack_NCSTATE26
```

### 2. Backend setup

```sh
cd backend
pip install -r requirements.txt
```

### 3. Frontend setup

```sh
cd ../frontend
npm install
```

### 4. Run locally

**Terminal 1 — start the backend:**

```sh
cd backend
python app.py
```

The API runs at `http://localhost:5050`.

**Terminal 2 — start the frontend:**

```sh
cd frontend
npm run dev
```

The app runs at `http://localhost:5173` (or the port Vite assigns). The frontend proxies `/submit` requests to the backend.

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/submit` | Verify a claim (expects `{ "message": "your claim" }`) |
| POST | `/api/verify` | Verify a claim (expects `{ "claim": "your claim" }`) |
| GET | `/api/health` | Health check |
| GET | `/api/sources` | List available fact-checking sources |

---

## 📄 License

This project was created for Hack_NCState 2026.
