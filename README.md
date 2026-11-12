# Job-Search Agent Bot

A Telegram bot that finds job and apprenticeship (Ausbildung) listings for a candidate and prepares the applications. It works for **several candidates ("clients") from one bot**, with a human confirmation step before anything is sent.

> The source code of this project is private (client work). This page describes what it does and how it is built.

## What it does
- **Job discovery:** searches for jobs and Ausbildung places, combining direct searches of applicant-tracking-system (ATS) platforms with a web-search discovery layer. Results are scored and filtered for relevance to the candidate's profile.
- **Candidate profiles:** parses an uploaded CV (PDF or Word, with OCR for images) with an LLM to build a profile, and keeps it in a profile database. Several candidates can be managed side by side.
- **Application materials:** generates company-specific cover letters and motivation text with an LLM, and builds a tailored CV as a Word document.
- **Application drafts:** prepares email applications and application-form drafts, with screenshots of filled forms for review.
- **Safety checks:** validation layers check generated text for integrity and truthfulness (for example, it must not claim qualifications the candidate does not have).
- **Confirm-before-send flows:** bulk sending and form submission need an explicit confirm command, with daily limits and randomized delays between emails.
- **Tracking:** an application store, follow-up reminders, an "already submitted" list, and an inbox tracker that watches replies.
- **Campaigns:** can run bulk campaigns from an Excel file and report on them.
- **Timers:** scheduled automatic job runs with locks, scan limits and retry rules.

## Stack
Python, Telegram Bot API (long polling), asyncio, an OpenAI-compatible LLM API, pdfplumber, python-docx, email sending, local data stores, browser automation for form drafts.

## How it is run
- Runs as a managed service on a Linux server, configured through environment variables.
- Delivered and handed over with project documentation.

## Context
Built at Arika (2024 - 2026) as one of five production services I delivered and handed over.

## Contact
Amir Hossein Fotoohi - ahfotoohi@gmail.com - [LinkedIn](https://linkedin.com/in/amir-hossein-fotoohi-411429390)
