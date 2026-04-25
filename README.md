
🛡️ ThreatLens AI — Unified Phishing Intelligence Platform  

ThreatLens AI is a full-stack phishing detection platform that analyzes suspicious URLs and emails using machine learning, NLP, and campaign intelligence. It provides clear verdicts, explainable insights, and real-time threat analysis.

---

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

---

⚙️ Setup Instructions  

🔧 Prerequisites  
- Python 3.10+  
- Node.js 18+  
- VS Code (recommended)  

---

🐍 Backend Setup  

Step 1:  
cd threatlens/backend  

Step 2:  
python -m venv venv  

Step 3 (Activate environment):  

Windows:  
venv\Scripts\activate  

Mac/Linux:  
source venv/bin/activate  

Step 4:  
pip install -r requirements.txt  

Step 5:  
python -m spacy download en_core_web_sm  

Step 6 (Optional API setup):  
cp .env.example .env  
Add your Anthropic API key inside .env  

Note: The app works without an API key using rule-based explanations.  

Step 7:  
uvicorn main:app --reload --port 8000  

Backend runs at: http://localhost:8000  
API Docs: http://localhost:8000/docs  

---

⚛️ Frontend Setup  

Step 1:  
cd threatlens/frontend  

Step 2:  
npm install  

Step 3:  
npm start  

Frontend runs at: http://localhost:3000  

---

🚀 How to Use  

1. Open http://localhost:3000  
2. Go to Scanner  
3. Select URL or Email  
4. Paste suspicious input  
5. Click Analyze Now  

Results include:  
- Verdict (Safe or Phishing)  
- AI Explanation  
- Threat Report Card  
- Campaign Intelligence  

---

🧪 Test Inputs  

Phishing URLs:  
http://paypa1-secure-login.tk/verify?id=usr123  
http://amaz0n-account-suspended.xyz/reactivate  
http://192.168.1.1/admin/login.php?session=abc  

Safe URLs:  
https://google.com/search?q=cybersecurity  
https://github.com/  

Phishing Email:  

From: noreply@paypai-support.com  
Subject: URGENT: Your account will be SUSPENDED!  

Dear Valued Customer,  
We have detected unusual login. Click here immediately:  
http://bit.ly/fix-now  

Failure to act within 24 hours will result in account suspension.  

---

🔑 API Endpoints  

POST   /api/scan       - Scan URL or email  
GET    /api/history    - Retrieve scan history  
GET    /api/stats      - Session statistics  
GET    /api/campaigns  - Known phishing campaigns  
GET    /api/health     - Health check  

---

📌 Key Features  

- URL & Email phishing detection  
- AI-powered explanations  
- Multi-layer threat scoring  
- Campaign intelligence tracking  
- Dashboard with analytics  

---

📝 Notes  

- Works without API key  
- Suitable for academic and real-world use  
- Easily extendable for production  
