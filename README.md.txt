🛡️ ThreatLens AI — Unified Phishing Intelligence Platform

ThreatLens AI is a full-stack phishing detection platform that analyzes suspicious URLs and emails using machine learning, NLP, and campaign intelligence. It provides clear verdicts, explainable insights, and real-time threat analysis.

📁 Project Structure
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
    ├── public/index.html
    ├── package.json
    └── src/
        ├── App.js
        ├── index.js
        ├── index.css
        ├── api/api.js
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
⚙️ Setup Instructions
🔧 Prerequisites
Python 3.10+
Node.js 18+
VS Code (recommended)
🐍 Backend Setup
cd threatlens/backend
python -m venv venv
Activate Virtual Environment
# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
Install Dependencies
pip install -r requirements.txt
Install spaCy Model
python -m spacy download en_core_web_sm
Configure Environment Variables (Optional)
cp .env.example .env
# Add your Anthropic API key in .env

ℹ️ The application works without an API key using rule-based explanations.

Run Backend Server
uvicorn main:app --reload --port 8000
Backend: http://localhost:8000
API Docs: http://localhost:8000/docs
⚛️ Frontend Setup
cd threatlens/frontend
npm install
npm start
Frontend: http://localhost:3000
🚀 How to Use
Open http://localhost:3000
Navigate to 🔍 Scanner
Select input type (URL or Email)
Paste suspicious content
Click Analyze Now
🧾 Output Includes
✅/🚨 Verdict — Safe or Phishing with confidence
🤖 AI Explanation — Plain-English reasoning
📋 Threat Report Card — Multi-dimensional scoring
🗺️ Campaign Intelligence — Attack pattern insights
🧪 Test Inputs
⚠️ Phishing URLs
http://paypa1-secure-login.tk/verify?id=usr123
http://amaz0n-account-suspended.xyz/reactivate
http://192.168.1.1/admin/login.php?session=abc
✅ Safe URLs
https://google.com/search?q=cybersecurity
https://github.com/
📧 Phishing Email
From: noreply@paypai-support.com
Subject: URGENT: Your account will be SUSPENDED!

Dear Valued Customer,
We have detected unusual login. Click here immediately:
http://bit.ly/fix-now

Failure to act within 24 hours will result in account suspension.
🔑 API Endpoints
Method	Endpoint	Description
POST	/api/scan	Scan URL or email
GET	/api/history	Retrieve scan history
GET	/api/stats	Session statistics
GET	/api/campaigns	Known phishing campaigns
GET	/api/health	Health check
📌 Key Features
🔍 URL & Email phishing detection
🤖 AI-powered explainability
📊 Multi-layer threat scoring
🗺️ Campaign tracking system
📈 Dashboard with analytics
📝 Notes
Works without API key (fallback logic included)
Designed for academic + real-world cybersecurity use
Easily extendable for production systems