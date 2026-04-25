# 🛡️ ThreatLens AI — Unified Phishing Intelligence Platform

ThreatLens AI is a full-stack phishing detection platform that analyzes suspicious URLs and emails using machine learning, NLP, and campaign intelligence. It provides clear verdicts, explainable insights, and real-time threat analysis.

## 📁 Project Structure

```text
threatlens/
├── backend/
│   ├── main.py              # FastAPI server (entry point)
│   ├── url_features.py      # URL feature extractor
│   ├── email_features.py    # Email NLP feature extractor
│   ├── campaign.py          # Fingerprinting + campaign database
│   ├── explainer.py         # AI explanation generator
│   ├── requirements.txt     # Python dependencies
│   └── .env.example         # Copy to .env and add API key
│
└── frontend/
    ├── public/
    │   └── index.html
    ├── package.json
    └── src/
        ├── App.js
        ├── index.js
        ├── index.css
        ├── api/
        │   └── api.js
        ├── components/
        │   ├── Navbar.js
        │   ├── VerdictBadge.js
        │   ├── ReportCard.js
        │   └── CampaignCard.js
        └── pages/
            ├── Scanner.js
            ├── Dashboard.js
            ├── Campaigns.js
            └── About.js
```

## ⚙️ Setup Instructions

### 🔧 Prerequisites
- **Python** 3.10+
- **Node.js** 18+
- **VS Code** (recommended)

### 🐍 Backend Setup

1. **Navigate to the backend directory**
   ```bash
   cd threatlens/backend
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   ```

3. **Activate the Virtual Environment**
   - **Windows:**
     ```cmd
     venv\Scripts\activate
     ```
   - **macOS/Linux:**
     ```bash
     source venv/bin/activate
     ```

4. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Install spaCy Model**
   ```bash
   python -m spacy download en_core_web_sm
   ```

6. **Configure Environment Variables (Optional)**
   ```bash
   cp .env.example .env
   ```
   > Add your Anthropic API key in the newly created `.env` file.
   > 
   > ℹ️ *Note: The application works without an API key by using rule-based explanations.*

7. **Run the Backend Server**
   ```bash
   uvicorn main:app --reload --port 8000
   ```
   - **Backend URL:** http://localhost:8000
   - **API Docs:** http://localhost:8000/docs

### ⚛️ Frontend Setup

1. **Navigate to the frontend directory**
   ```bash
   cd threatlens/frontend
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Start the Development Server**
   ```bash
   npm start
   ```
   - **Frontend URL:** http://localhost:3000

## 🚀 How to Use

1. Open http://localhost:3000 in your browser.
2. Navigate to 🔍 **Scanner**.
3. Select the input type (URL or Email).
4. Paste the suspicious content.
5. Click **Analyze Now**.

### 🧾 Output Includes
- **✅/🚨 Verdict** — Safe or Phishing with confidence score.
- **🤖 AI Explanation** — Plain-English reasoning for the verdict.
- **📋 Threat Report Card** — Multi-dimensional scoring of the threat.
- **🗺️ Campaign Intelligence** — Attack pattern insights.

## 🧪 Test Inputs

### ⚠️ Phishing URLs
- `http://paypa1-secure-login.tk/verify?id=usr123`
- `http://amaz0n-account-suspended.xyz/reactivate`
- `http://192.168.1.1/admin/login.php?session=abc`

### ✅ Safe URLs
- `https://google.com/search?q=cybersecurity`
- `https://github.com/`

### 📧 Phishing Email
**From:** `noreply@paypai-support.com`  
**Subject:** `URGENT: Your account will be SUSPENDED!`  
```text
Dear Valued Customer,
We have detected unusual login. Click here immediately:
http://bit.ly/fix-now

Failure to act within 24 hours will result in account suspension.
```

## 🔑 API Endpoints

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/api/scan` | Scan URL or email |
| `GET` | `/api/history` | Retrieve scan history |
| `GET` | `/api/stats` | Session statistics |
| `GET` | `/api/campaigns` | Known phishing campaigns |
| `GET` | `/api/health` | Health check |

## 📌 Key Features

- 🔍 **URL & Email** phishing detection
- 🤖 **AI-powered** explainability
- 📊 **Multi-layer** threat scoring
- 🗺️ **Campaign tracking** system
- 📈 **Dashboard** with analytics

## 📝 Notes
- The application includes fallback logic to work seamlessly without an API key.
- Designed for academic and real-world cybersecurity use cases.
- Easily extendable for production-level systems.
