# HireIQ — Smart Talent Engagement Platform

> Hackathon submission for **Deccan AI Catalyst** — AI-Powered Talent Scouting & Engagement Agent challenge.

## 🎯 What HireIQ Does

HireIQ is an intelligent talent engagement platform that eliminates the manual grind of talent screening. Recruiters input a Job Description and a pool of candidates — HireIQ returns a scored, ranked, and explainable shortlist ready for action.

**Live Demo**: [YOUR_DEPLOYED_URL_HERE]  
**Demo Video**: [YOUR_VIDEO_LINK_HERE]

---

## 🏗 Architecture

### Four-Stage AI Pipeline

```
Input JD + Candidates
        │
        ▼
┌─────────────────┐
│  Stage 1:       │  ← Claude AI extracts: required skills, experience band,
│  JD Parsing     │    domain expertise, culture signals → creates scoring rubric
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Stage 2:       │  ← Each candidate evaluated against rubric
│  Match Scoring  │    Dimensions: skill fit (40%), exp fit (25%),
│  (0–100)        │    domain (20%), leadership signals (15%)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Stage 3:       │  ← Simulated conversational outreach
│  Interest       │    AI analyses: response enthusiasm, specificity,
│  Scoring (0–100)│    career alignment → Interest Score
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Stage 4:       │  ← Combined = 0.6 × Match + 0.4 × Interest
│  Ranked Output  │    Full audit trail, recruiter-ready
└─────────────────┘
```

### Scoring Formula

```
Combined Score = (Match Score × 0.6) + (Interest Score × 0.4)
```

| Component | Weight | Inputs |
|-----------|--------|--------|
| Match Score | 60% | Skill coverage, experience fit, domain relevance, growth signals |
| Interest Score | 40% | Profile trajectory, conversational enthusiasm, career alignment |

---

## ✨ Key Features

- **JD Parsing**: Automatically extracts structured requirements from raw JD text
- **Explainable Scoring**: Every score comes with a plain-English rationale
- **Conversational Outreach Simulation**: Live interest meter updates as conversation deepens
- **4-Step Workflow**: Guided interface — Input → Results → Engage → Shortlist
- **Zero Backend**: Runs entirely client-side, no server required

---

## 🛠 Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| AI Engine | Anthropic Claude API (`claude-sonnet-4-20250514`) |
| Fonts | Google Fonts (Playfair Display, DM Sans) |
| Hosting | GitHub Pages / Netlify |
| Build | None — open `index.html` directly |

---

## ⚡ Quick Start

```bash
# Clone
git clone https://github.com/YOUR_USERNAME/hireiq-ai
cd hireiq-ai

# Run locally (no install needed)
open index.html

# OR with a local server
npx serve .
# Visit: http://localhost:3000
```

---

## 📋 Sample Inputs & Outputs

### Input — Job Description
```
We are hiring a Product Manager to lead our payments platform. 
Requirements: 3+ years PM experience, fintech/SaaS domain, 
data literacy (SQL), cross-functional collaboration with engineering.
Nice to have: experience with Stripe, Razorpay or similar APIs.
```

### Input — Candidate Pool
```
Neha Gupta | Product strategy, Fintech, SQL | 4 years | Ex-Razorpay PM
Rahul Verma | Agile, B2B SaaS, analytics | 5 years | PM at Freshworks, IIM-A MBA
Anjali Singh | Mobile, growth, A/B testing | 3 years | Series A startup PM lead
```

### Output — Ranked Shortlist
| # | Candidate | Match | Interest | Combined |
|---|-----------|-------|----------|---------|
| 🥇 1 | Neha Gupta | 94 | 88 | 92 |
| 🥈 2 | Rahul Verma | 85 | 82 | 84 |
| 🥉 3 | Anjali Singh | 74 | 79 | 76 |

---

## 📁 File Structure

```
hireiq-ai/
├── index.html      # Complete application — single file
└── README.md       # This documentation
```

---

## 🔒 Notes

- API calls are made client-side. For production deployment, route through a backend to protect your API key.
- No user data is stored — fully stateless.

---

## 📄 License

MIT
