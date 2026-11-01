# ClaimPilot AI – Backend

AI-powered Medical Insurance Claims Review System.

## Overview

ClaimPilot AI assists insurance employees in reviewing medical insurance claims through document processing, information extraction, validation, and evidence-based review summaries.

AI supports human reviewers; it does not independently approve or reject claims.

## Tech Stack

- Python 3.11
- FastAPI
- Uvicorn
- Pydantic
- PostgreSQL (planned)
- SQLAlchemy (planned)

## Project Structure

```text
claimpilot-ai-backend/
├── app/
│   ├── __init__.py
│   └── main.py
├── tests/
├── requirements.txt
├── README.md
└── .gitignore
```

## Setup

Create and activate the virtual environment:

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
python -m pip install -r requirements.txt
```

## Run the Application

```powershell
uvicorn app.main:app --reload
```

## API Documentation

Once the application is running:

- Swagger UI: http://127.0.0.1:8000/docs
- Health Check: http://127.0.0.1:8000/health

## Current Status

Milestone 1 – Project Foundation & System Design.

- [x] Backend project created
- [x] Python virtual environment configured
- [x] FastAPI and Uvicorn installed
- [ ] Initial API created
- [ ] PostgreSQL integration
- [ ] Claim management APIs
- [ ] Automated tests


## GitHub Push Verification

Testing GitHub authentication with shubhammahajan28.
Git identity verification completed.