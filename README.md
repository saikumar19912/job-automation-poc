# job-automation-poc

Repository structure:

job-automation-poc/
│
├── README.md
│
├── workflows/
│   └── n8n-job-ingestion-poc.json
│
├── data/
│   ├── sample-input/
│   │   └── indeed-sample.json
│   │
│   └── sample-output/
│       └── jobs-sheet-sample.csv
│
├── docs/
│   ├── workflow-overview.md
│   └── data-schema.md
│
├── screenshots/
│   ├── n8n-workflow.png
│   └── job-output-sheet.png
│
└── .gitignore

This commit adds the repository folder/file structure and placeholder files.

# Automated Job Ingestion – Proof of Concept (POC)

## Overview
This project is a **Proof of Concept (POC)** to validate automated ingestion of job postings from external job portals into a structured format using workflow automation.

The POC demonstrates end-to-end feasibility of:
- Consuming real job data in JSON format
- Normalizing job fields
- Storing results in a structured sheet for further processing

---

## Objective
To confirm that job postings from platforms like **Indeed** can be automatically collected, processed, and stored in a standardized schema for future automation such as filtering, AI-based resume matching, and direct job applications.

---

## Scope of POC
- Single job source: **Indeed**
- Manual workflow trigger for controlled execution
- Flat storage using **Google Sheets / Excel**
- Focus on correctness and data mapping (not scale)

---

## Tech Stack
- **Automation Platform:** n8n  
- **Data Format:** JSON  
- **Storage:** Google Sheets / Excel  
- **Trigger Type:** Manual Trigger  

---

## Workflow Steps
1. Manual trigger starts the workflow
2. Job data is received in JSON format
3. Fields are safely extracted and validated
4. Each job record is appended as a new row in the sheet
5. Optional or missing fields are handled gracefully

---

## Data Schema
| Column Name        | Description                             |
|-------------------|-----------------------------------------|
| job_uid           | Unique internal job identifier          |
| source            | Job source (Indeed)                     |
| source_job_id     | Job ID extracted from source URL        |
| title             | Job title                               |
| company           | Company name                            |
| location          | Job location                            |
| employment_type   | Full-time / Contract (if available)    |
| experience_level  | (Future enhancement)                     |
| skills            | (Future enhancement)                     |
| jd_raw            | Raw job description (future)             |
| apply_url         | Direct job application link             |
| posted_date       | (Future enhancement)                     |
| fetched_at        | Timestamp of ingestion                  |
| status            | Job processing status                    |

---

## POC Results
- Successfully ingested multiple job postings
- Each job mapped to one structured row
- Workflow executed without errors
- Optional fields handled without breaking the flow

---

## Future Enhancements
- Add multiple job sources (LinkedIn, Dice, etc.)
- Deduplication logic across platforms
- AI-based job relevance scoring
- Resume customization using AI
- Automated job application submission
- Scheduled and event-based triggers
- Database storage (PostgreSQL / MongoDB)

---

## How to Run the POC
1. Import the workflow into n8n
2. Configure Google Sheets credentials
3. Trigger the workflow manually
4. Verify appended job records in the sheet

---

## Conclusion
This POC confirms that automated job ingestion and normalization is technically feasible. The solution provides a strong foundation for building a scalable AI-powered job automation platform.

