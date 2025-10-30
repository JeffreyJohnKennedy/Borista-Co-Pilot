# ☕ **Millie – The Dutch Bros Co-Pilot**

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![AWS](https://img.shields.io/badge/Cloud-AWS-orange?logo=amazonaws)
![FastAPI](https://img.shields.io/badge/Backend-FastAPI-teal?logo=fastapi)
![React](https://img.shields.io/badge/Frontend-React-blue?logo=react)
![LLM](https://img.shields.io/badge/AI-LLM%20%2B%20BERT-purple)
![Hackathon](https://img.shields.io/badge/Hackathon-2nd%20Prize%20Winner-gold)
![License](https://img.shields.io/badge/License-MIT-green)

---

## ✨ Overview

**Millie** is an **AI Co-Pilot for Dutch Bros Broistas**, automating order entry while preserving genuine customer interaction.  
It listens to live customer–broista conversations, transcribes speech to text, identifies drink orders and modifiers, predicts rush patterns, and updates the POS automatically — *“Automation does the typing; broistas keep the magic.”*

---

## 🎯 Problem Statement

- ⏱️ **Typing steals time:** Manual entry of complex drinks and modifiers is slow and error-prone.  
- 🕐 **Late customer context:** DutchPass QR is scanned only at checkout, losing personalization opportunities.  
- 💬 **No “usual” prompt:** No automatic personalization during rush hours.  
- ⚡ **KDS not proactive:** No shared ETAs or rush alerts between broistas.  
- 🧩 **Training overhead:** New broistas struggle to learn the manual POS flow.

---

## 💡 Solution: *Millie – The Dutch Bros Co-Pilot*

| Feature | Description |
|----------|--------------|
| 🎙️ **Voice-to-Order** | Real-time transcription and order parsing from broista–customer speech. |
| 📊 **DutchPass QR Analytics** | Identifies loyal customers early and preloads favorites. |
| 🧠 **Smart Recommendation Engine** | Suggests modifiers and “Frequently Bought Together” items. |
| ⚙️ **KDS Automation** | Syncs drink prep timing across all stations with shared ETAs. |
| 🔔 **Predictive Ops (Rush Radar)** | Alerts staff of peak times with load-balancing notifications. |

---

## 🏗️ System Workflow

The architecture combines AWS services with FastAPI and Claude Sonnet 3.5:

```
DutchPass (QR) → Frontend (React)
               ↓
          FastAPI Gateway
               ↓
         AWS Transcribe
               ↓
       Claude Sonnet 3.5 (LLM)
               ↓
      Matcher & Pricing Engine
               ↓
     POS/KDS Adapter  →  KDS Board
                    ↘
                    Notifier (Rush Radar)
```

This pipeline converts **voice → structured JSON → POS order**, fully automated in real time.

---

## 🧰 Tech Stack

| Layer | Technologies |
|-------|---------------|
| **Frontend** | React.js, Tailwind, WebSocket |
| **Backend** | FastAPI, Python |
| **AI / ML** | AWS Transcribe, Claude Sonnet 3.5 (via Bedrock), BERT, Smart Recommender |
| **Data / Storage** | AWS S3, DynamoDB, Historical CSVs |
| **Infrastructure** | AWS Lambda, EC2, mTLS Gateway, Docker |
| **Security** | Server-side SigV4 auth, mTLS encryption |
| **Analytics** | QR-based customer insights, ETA/rush forecasting |

---

## ⚙️ Setup Guide

### 1️⃣ Clone Repository
```bash
git clone https://gitlab.com/dutchbros/hackathon/team-1/spark.git
cd spark
```

### 2️⃣ Configure Environment
Create a `.env` file in the backend folder:
```bash
AWS_REGION=us-west-2
DUTCH_BROS_API_KEY=your_api_key
```

### 3️⃣ Install Backend & Frontend Dependencies
```bash
cd backend && pip install -r requirements.txt
cd ../frontend && npm install
```

## 🧪 Product Demo

> “I’d like a Tuxedo Hot Chai, large, extra hot.”  
Millie transcribes → identifies modifiers → sends JSON → adds drink to cart in the POS UI.

---

## 📈 Business Impact

| Metric | Impact |
|---------|---------|
| ⏳ **Speed** | Typing removed → Line times drop, especially during peak hours (7–10 AM, 11–2 PM, 7–10 PM). |
| ✅ **Accuracy** | Drink modifiers and add-ons captured correctly; remakes reduced. |
| 💬 **Connection** | Broistas stay “eyes-up”; “The Usual” becomes one-tap authentic. |
| 🧘 **Operational Calm** | Rush Radar + shared ETAs stabilize operations. |
| 🔐 **Security** | End-to-end encryption with mTLS and SigV4; no exposed AWS keys. |

---

## 🚀 Millie 2.0 (Next Phase)

- 🔁 Loyalty API + Personalized Offers  
- 🔉 Improved noise handling for multi-speaker environments  
- 📱 Kiosk & Mobile Voice Integration + A/B Testing  
- 📦 Inventory Forecasting from Real-Time Demand

---

## 🧑‍💻 Team 2169 – Arizona State University

| Name | Role | School |
|------|------|---------|
| **Lekshman Babu** | Data Science Lead | Ira A. Fulton School of Engineering |
| **Maanesh Mohanraj** | ML Engineer | Ira A. Fulton School of Engineering |
| **Ben Stewart** | Software Engineer | Ira A. Fulton School of Engineering |
| **Vijai Kumar** | Data Scientist | Ira A. Fulton School of Engineering |
| **Jeffrey John Kennedy** | Business Analyst | W. P. Carey School of Business |

---

## 🪪 License

This project is licensed under the **MIT License**.  
See `LICENSE` for details.

---

## 📫 Contact

📧 team.spark@dutchbros.ai  
🌐 [Dutch Bros Hackathon Portal](https://dutchbros.com/hackathon)

---

> 🧠 *“Automation does the typing; broistas keep the magic.” — Millie, your Dutch Bros Co-Pilot*
