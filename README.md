# 🛡️ PhishGuard AI

### AI-Powered Phishing Webpage Identification & Browser Security Extension

PhishGuard AI is an AI-powered cybersecurity browser extension that detects **phishing, cloned, impersonated, and suspicious webpages** in real time.

It analyzes not only the URL, but also the **domain identity, webpage structure, login forms, redirects, brand identity, and visual similarity** with legitimate websites to determine whether a webpage is trustworthy.

---

## 🚨 Problem

Phishing attackers create fake websites that closely imitate legitimate banking, payment, government, educational, social-media, and business websites.

These websites can copy:

* Logos
* Colors
* Layouts
* Login pages
* Buttons
* Fonts
* Navigation
* Overall website design

As a result, users may believe they are using the original website and enter sensitive information such as passwords, OTPs, card details, or other credentials.

Traditional phishing detection systems often rely heavily on known malicious URLs and blacklists. Newly created phishing websites may not yet be present in these databases.

---

## 💡 Solution

**PhishGuard AI** acts as a security layer between the user and the webpage.

The extension analyzes the current webpage and combines multiple security signals:

```text
URL Analysis
     ↓
Domain Verification
     ↓
Brand Identity Detection
     ↓
DOM & HTML Analysis
     ↓
Login/Form Detection
     ↓
Redirect Analysis
     ↓
Visual UI Comparison
     ↓
Machine Learning
     ↓
Risk Scoring
     ↓
Security Verdict
```

The system determines whether the webpage is:

* 🟢 **SAFE**
* 🟡 **SUSPICIOUS**
* 🟠 **HIGH RISK**
* 🔴 **PHISHING**
* ⚪ **LOCAL / UNKNOWN**

---

## ⭐ Key Features

### 🔍 1. URL Analysis

Detects:

* Suspicious URLs
* Long URLs
* IP-based URLs
* Suspicious parameters
* URL encoding
* Unusual ports
* Suspicious keywords

### 🌐 2. Domain Verification

Checks whether the webpage belongs to the organization it claims to represent.

Example:

```text
Claimed Brand: Microsoft

Current Domain:
microsoft-login-security.example.com

Official Domain:
microsoft.com

❌ Domain Mismatch
```

---

### 🎭 3. Phishing & Brand Impersonation Detection

Detects webpages pretending to be:

* Banks
* Payment services
* Government websites
* Universities
* Companies
* Social-media platforms
* Shopping websites
* Job portals
* Cloud services

---

### 🖥️ 4. Cloned Website Detection

Compares the suspicious webpage with the legitimate website.

The system analyzes:

* Layout
* Colors
* Logo
* Buttons
* Forms
* Page structure
* Text
* Visual appearance

Example:

```text
Official Website UI
        ↕
Visual Comparison
        ↕
Suspicious Website UI

Similarity: 93%

⚠ Possible Cloned Website
```

---

### 🔐 5. Credential Form Detection

Detects pages requesting:

* Username
* Password
* OTP
* PIN
* CVV
* Card information
* Banking credentials

It also checks whether credentials are submitted to an unexpected domain.

---

### 🏠 6. Localhost & Local Server Detection

PhishGuard AI recognizes:

```text
localhost
127.0.0.1
192.168.x.x
10.x.x.x
172.16.x.x – 172.31.x.x
```

It does **not** automatically classify localhost as malicious.

For example:

```text
localhost:3000
+
Normal development application
=
⚪ LOCAL / UNKNOWN
```

But:

```text
localhost:3000
+
Bank UI clone
+
Bank logo
+
Password form
=
🔴 HIGH RISK
```

---

### 🔄 7. Redirect Analysis

Analyzes suspicious navigation such as:

```text
Website A
   ↓
Website B
   ↓
Website C
   ↓
Fake Login Page
```

---

### 🤖 8. AI/ML Detection

The project can use machine-learning models to classify webpages based on extracted cybersecurity features.

Possible model:

**Random Forest Classifier**

Input features may include:

* URL features
* Domain features
* HTML features
* Form features
* Redirect features
* Visual similarity
* DOM similarity
* Brand mismatch
* Security indicators

---

### 📊 9. Explainable Risk Score

Instead of simply saying:

```text
Phishing: 95%
```

PhishGuard AI explains why.

Example:

```text
🔴 PHISHING
Risk Score: 94/100

Reasons:

❌ Domain does not match official domain
⚠ Login form detected
⚠ Website UI strongly resembles official website
⚠ Suspicious redirect detected
⚠ Brand impersonation detected
```

---

## 🧠 Algorithms

PhishGuard AI can use the following algorithms and techniques:

### URL & Domain

* Levenshtein Distance
* Damerau-Levenshtein Distance
* Shannon Entropy
* Typosquatting Detection
* Unicode/Homograph Detection
* Punycode Detection

### Text & Webpage

* TF-IDF
* Cosine Similarity
* DOM Structural Analysis
* HTML Feature Extraction

### Visual Analysis

* Perceptual Hashing
* pHash
* dHash
* aHash
* SSIM
* Image Embeddings
* Cosine Similarity

### Machine Learning

* Random Forest
* Gradient Boosting
* XGBoost *(optional)*
* Cross Validation
* Precision
* Recall
* F1 Score
* ROC-AUC
* Confusion Matrix

---

## 🛠️ Technology Stack

### Browser Extension

* TypeScript
* JavaScript
* React
* Vite
* Tailwind CSS
* WebExtensions API
* Manifest V3

### Backend

* Python
* FastAPI
* SQLAlchemy
* Pydantic

### Machine Learning

* Python
* NumPy
* Pandas
* Scikit-learn
* OpenCV
* BeautifulSoup
* Joblib
* PyTorch *(optional)*

### Database

* PostgreSQL
* SQLite for development

### Development Tools

* Git
* GitHub
* VS Code
* Docker
* Postman
* Chrome DevTools

---

## 🏗️ Architecture

```text
                ┌─────────────────┐
                │    Webpage      │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ PhishGuard AI   │
                │ Browser         │
                │ Extension       │
                └────────┬────────┘
                         │
        ┌────────────────┼────────────────┐
        ▼                ▼                ▼
   URL Analyzer     DOM Analyzer    Visual Analyzer
        │                │                │
        ▼                ▼                ▼
 Domain Analyzer   Form Detector    UI Similarity
        │                │                │
        └────────────────┼────────────────┘
                         ▼
                Identity Verification
                         │
                         ▼
                 ML Classification
                         │
                         ▼
                  Risk Engine
                         │
                         ▼
                Explainable Result
                         │
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
        SAFE        SUSPICIOUS      PHISHING
```

---

## 📁 Project Structure

```text
phishguard-ai/
│
├── extension/
│   ├── src/
│   │   ├── background/
│   │   ├── content/
│   │   ├── popup/
│   │   ├── dashboard/
│   │   ├── warning/
│   │   ├── analyzers/
│   │   ├── detectors/
│   │   ├── services/
│   │   ├── utils/
│   │   └── types/
│   │
│   ├── manifest.json
│   ├── package.json
│   └── vite.config.ts
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   └── main.py
│   │
│   ├── tests/
│   └── requirements.txt
│
├── ml/
│   ├── datasets/
│   ├── features/
│   ├── models/
│   ├── training/
│   └── evaluation/
│
├── database/
│   └── migrations/
│
├── docs/
│   ├── architecture.md
│   ├── algorithms.md
│   └── security.md
│
├── docker-compose.yml
└── README.md
```

---

## 🚀 Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/phishguard-ai.git

cd phishguard-ai
```

### 2. Install extension dependencies

```bash
cd extension

npm install
```

### 3. Start the development server

```bash
npm run dev
```

### 4. Build the extension

```bash
npm run build
```

The production extension will be generated in the build/output directory configured by the project.

---

## 🐍 Backend Setup

Go to the backend directory:

```bash
cd backend
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the FastAPI server:

```bash
uvicorn app.main:app --reload
```

API documentation:

```text
http://127.0.0.1:8000/docs
```

---

## 🧪 Testing

Run backend tests:

```bash
pytest
```

Test the extension using safe test webpages representing:

* Legitimate website
* Typosquatting website
* Cloned website
* Fake login page
* Localhost webpage
* Suspicious redirect
* Unknown website
* Brand impersonation page

---

## 🔐 Privacy & Security

PhishGuard AI is designed with privacy in mind.

The system should never:

* Store passwords
* Store OTPs
* Store card numbers
* Store authentication tokens
* Collect unnecessary personal information

Where possible, analysis should be performed locally in the browser.

External analysis should use only the minimum required information and must follow user consent and applicable privacy requirements.

---

## 🎯 Hackathon Innovation

The main innovation of PhishGuard AI is that it does not depend only on:

```text
URL → Blacklist → Phishing
```

Instead, it combines:

```text
Domain Identity
       +
URL Analysis
       +
DOM Analysis
       +
Credential Detection
       +
Brand Detection
       +
Visual Similarity
       +
Redirect Analysis
       +
Machine Learning
       ↓
Hybrid Risk Assessment
```

The system focuses on an important phishing scenario:

> **A webpage may look exactly like the original website while actually being hosted on a different domain.**

PhishGuard AI attempts to identify this mismatch before the user submits sensitive information.

---

## 🎬 Demo Scenarios

### Scenario 1 — Legitimate Website

```text
Official Domain
      ↓
Domain Verified
      ↓
UI Verified
      ↓
🟢 SAFE
```

### Scenario 2 — Cloned Website

```text
Different Domain
      ↓
High UI Similarity
      ↓
Login Form
      ↓
Domain Mismatch
      ↓
🔴 PHISHING
```

### Scenario 3 — Localhost Clone

```text
localhost:3000
      ↓
Bank UI Clone
      ↓
Password Form
      ↓
Brand Impersonation
      ↓
🔴 HIGH RISK
```

---

## 📈 Future Scope

Future versions can include:

* More browser support
* Real-time threat-intelligence integration
* Improved deep-learning models
* Continuous website reference updates
* Mobile browser protection
* Enterprise security dashboard
* Community phishing reporting
* Multilingual phishing detection
* QR-code landing-page analysis
* Email-to-webpage phishing analysis

---

## ⚠️ Disclaimer

PhishGuard AI is a cybersecurity research and educational project.

No phishing-detection system can guarantee 100% accuracy. A website classified as safe should not automatically be considered completely trustworthy.

Users should continue to follow standard cybersecurity practices and avoid entering sensitive information on suspicious webpages.

---

## 👨‍💻 Project

**Project:** PhishGuard AI
**Domain:** Cyber Security
**Sub-Domain:** Web Security / Phishing Detection
**Technology:** AI/ML + Browser Extension + Web Security

Built for **LT HackFest 2026 — Open Innovation**.
