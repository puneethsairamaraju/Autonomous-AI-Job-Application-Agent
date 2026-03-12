# Autonomous AI Job Application Agent

A **production-grade AI-powered career assistant** that automates the entire job application workflow — from **job discovery to tailored applications and interview preparation**.

Built using **LLMs, RAG, semantic search, and modern backend architecture**, the system helps job seekers optimize resumes, generate cover letters, prepare interviews, and track applications in one unified platform.

---

# Project Overview

The **Autonomous AI Job Application Agent** is an end-to-end AI system designed to automate and optimize job applications.

The system can:

- Search and analyze job postings
- Extract required skills
- Score resume-job compatibility (ATS match)
- Tailor resumes using AI
- Generate personalized cover letters
- Prepare interview questions and answers
- Track job applications

The platform works **even without API access** by automatically switching to rule-based fallback logic.

---

# System Architecture

```
Frontend
(Streamlit UI)

        │
        ▼

Backend API
(FastAPI + Uvicorn)

        │
        ▼

AI Engine
(Python modules)

        │
        ├── Resume Parsing
        ├── Skill Extraction
        ├── ATS Scoring
        ├── Resume Tailoring
        ├── Cover Letter Generation
        └── Interview Preparation

        │
        ▼

Vector Search
FAISS + Sentence Transformers

        │
        ▼

Database
SQLite (Application Tracking)
```

---

# Project Structure

```
pp/
├── job_agent/
│   ├── config.py
│   ├── models.py
│   ├── utils.py
│   ├── scraper.py
│   ├── skill_extractor.py
│   ├── ats_scorer.py
│   ├── resume_tailor.py
│   ├── cover_letter.py
│   ├── interview_prep.py
│   └── tracker.py
│
├── api/
│   └── main.py
│
├── ui/
│   └── app.py
│
├── data/
│   ├── applications.db
│   └── sample_resume.txt
│
├── .env.example
├── requirements.txt
├── Dockerfile
└── docker-compose.yml
```

---

# Features

| Feature | AI Mode | Offline Fallback |
|------|------|------|
| Job Scraping | Indeed scraper | Mock job dataset |
| Resume Parsing | LLM JSON extraction | Regex heuristics |
| Skill Extraction | LLM + NLP | Keyword scanning |
| ATS Scoring | Semantic + keyword matching | Keyword only |
| Resume Tailoring | RAG-based rewriting | Gap analysis |
| Cover Letter Generation | LLM generation | Template |
| Interview Preparation | AI Q&A generation | Generic questions |
| Application Tracking | SQLite database | Always available |

---

# Tech Stack

| Layer | Technology |
|------|------|
| LLM | Google Gemini |
| Embeddings | Sentence Transformers |
| Vector Search | FAISS |
| Backend API | FastAPI |
| Frontend | Streamlit |
| Charts | Plotly |
| Database | SQLite |
| PDF Parsing | pdfplumber |
| DOCX Parsing | python-docx |
| Data Models | Pydantic |

---

# Streamlit UI Pages

### Resume Upload
Upload **PDF / DOCX / TXT** resumes with two-stage processing:

- Instant text extraction
- Optional AI parsing

### Job Search
Search job listings and automatically extract required skills.

### ATS Scorer
Calculate **resume-job match percentage** using semantic similarity and keyword matching.

### Resume Tailor
Generate an optimized resume version for a specific job.

Includes:

- Tailored resume
- List of changes
- Side-by-side comparison

### Cover Letter Generator
Generate personalized cover letters with selectable tone:

- Professional
- Enthusiastic
- Concise

### Interview Preparation

Generate interview preparation materials including:

- Technical questions
- Behavioral questions
- Preparation tips

### Application Tracker

Track all job applications with:

- Status updates
- Funnel analytics
- Application history

---

# FastAPI Endpoints

| Method | Endpoint | Purpose |
|------|------|------|
| POST | /resume/parse | Parse resume file |
| POST | /resume/parse-text | Parse raw resume text |
| POST | /jobs/search | Search jobs |
| POST | /ats/score | Calculate ATS score |
| POST | /resume/tailor | Tailor resume |
| POST | /cover-letter/generate | Generate cover letter |
| POST | /interview/prepare | Generate interview prep |
| POST | /applications | Save application |
| GET | /applications | List applications |
| GET | /applications/{id} | Get application |
| PATCH | /applications/{id}/status | Update status |
| DELETE | /applications/{id} | Delete application |
| GET | /stats | Application statistics |

---

# Error Handling & Resilience

The system is designed to be **fully fault tolerant**.

Common API failures handled:

- Invalid API keys
- Model not found errors
- Rate limit errors
- Quota exhaustion

Fallback logic automatically switches to **rule-based systems**, ensuring the application remains fully functional.

---

# How to Run the Project

## 1. Install Dependencies

```bash
pip install -r requirements.txt
```

## 2. Configure API Key

Get an API key from:

https://aistudio.google.com/app/apikey

Edit `.env.example`:

```
GEMINI_API_KEY=your_api_key_here
```

## 3. Start Streamlit UI

```
streamlit run ui/app.py
```

## 4. Start Backend API

```
uvicorn api.main:app --reload --port 8000
```

## 5. Run Using Docker

```
docker-compose up
```

---

# Current Status

- All modules implemented
- Full UI + API integration
- Graceful offline fallback
- Docker support
- Production-ready architecture

---

# Future Improvements

- Multi-job resume optimization
- Autonomous job application agent
- Vector database integration
- LinkedIn job scraping
- Cloud deployment
- LLM agent workflows

---

# Author

**Puneeth Sai Rama Raju Kucherlapati**

AI / Machine Learning Engineer
