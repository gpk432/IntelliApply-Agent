# IntelliApply Agent
### AI-Powered Job Matching & Application Preparation System

## Overview
IntelliApply is an AI-driven system that automates key steps in the job application workflow. It parses a user’s resume, extracts structured profile information, discovers relevant job opportunities, evaluates fit using a hybrid ranking engine, and generates tailored documents including job-specific resumes and cover letters.

This project was built as part of the Kaggle + Google Agents Intensive Capstone (Enterprise Agents Track) and demonstrates practical multi-agent orchestration, reasoning with Gemini models, tool integration, and high-quality document generation.

## Key Features

### Resume Parsing & Profile Building
- Extracts text from PDF/DOCX resumes.
- Identifies skills, experience, education, and job preferences.
- Builds a reusable profile representation for subsequent ranking.

### Job Retrieval & Ingestion
- Scrapes or fetches job listings from online sources.
- Normalizes job descriptions into a consistent schema.

### Job Relevance Ranking
- Combines rule-based scoring with Gemini reasoning.
- Prioritizes roles based on skills, experience, seniority, and user-defined filters.

### Tailored Resume Generation
- Reorders skills based on relevance.
- Highlights projects and quantifiable achievements tailored to each job description.
- Produces clean, ATS-friendly PDF resumes.

### Cover Letter Generation
- Creates concise, role-specific cover letters using Gemini 2.0 Flash-Thinking.
- Includes personalized context derived from job requirements and resume highlights.

### Output Packaging
- All generated files are exported as PDF.
- Results include ranked jobs, tailored documents, and a session summary.

## System Architecture

The IntelliApply architecture is organized into discrete components grouped into two major subsystems: the Matching Engine and the Output Generation unit.

(Insert system_architecture.png here)

## Implementation Highlights

### 1. Resume Processing
Documents are converted to text using pymupdf and python-docx, then structured into segments such as Summary, Experience, Skills, and Education.

### 2. Multi-Agent Logic
The system uses modular agent patterns:
- Parsing Agent
- Matching Agent
- Ranking Agent
- Document Generation Agent

### 3. Job Ranking Engine
Employs keyword matching, skill overlap checks, preference matching, and Gemini-based scoring.

### 4. Document Generation
Uses FPDF2 for PDF assembly with dynamic templates and relevance-based positioning.

## Evaluation
Two synthetic job descriptions were manually labeled to validate ranking performance. The system accurately separated high-fit and low-fit jobs, confirming reliable baseline behavior.

## Repository Structure
```
IntelliApply-Agent/
│
├── notebook/
│   └── IntelliApply.ipynb
│
├── assets/
│   └── system_architecture.png
│   └── thumbnail.jpg
│
├── data/
│   └── sample_resume.txt
│
└── README.md
```

## How to Run
1. Open `notebook/IntelliApply.ipynb`
2. Enter your Gemini API key when prompted
3. Upload a resume
4. Provide job preferences
5. Review ranked jobs
6. Download generated PDFs

## Future Enhancements
- Direct job applications via API
- More resume templates and formatting
- Cloud deployment with Vertex AI Agent Engine
- Persistent user sessions
- Multi-resume optimization

## License
This project is published for academic and demonstration purposes.
