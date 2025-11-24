---
slug: github-schedule-gcp-chron-jobs-note-technical-overview
id: github-schedule-gcp-chron-jobs-note-technical-overview
title: schedule-gcp-chron-jobs
repo: justin-napolitano/schedule-gcp-chron-jobs
githubUrl: https://github.com/justin-napolitano/schedule-gcp-chron-jobs
generatedAt: '2025-11-24T18:45:50.492Z'
source: github-auto
summary: >-
  This repo helps you automate job scheduling on Google Cloud Run using Google
  Cloud Scheduler. It’s focused on running containerized workloads at set
  intervals—like hourly or daily.
tags: []
seoPrimaryKeyword: ''
seoSecondaryKeywords: []
seoOptimized: false
topicFamily: null
topicFamilyConfidence: null
kind: note
entryLayout: note
showInProjects: false
showInNotes: true
showInWriting: false
showInLogs: false
---

This repo helps you automate job scheduling on Google Cloud Run using Google Cloud Scheduler. It’s focused on running containerized workloads at set intervals—like hourly or daily.

## Key Components

- Dockerfile to containerize your Python script
- Commands for building and pushing Docker images to Google Container Registry
- Steps to create and deploy Cloud Run jobs
- Setup for scheduling via Cloud Scheduler

## Quick Start

1. Clone the repo:

   ```bash
   git clone https://github.com/justin-napolitano/schedule-gcp-chron-jobs.git
   cd schedule-gcp-chron-jobs
   ```

2. Update your Python script as needed.

3. Build and push your Docker image:

   ```bash
   gcloud builds submit --tag gcr.io/YOUR_PROJECT/YOUR_IMAGE:latest
   ```

4. Create the Cloud Run job:

   ```bash
   gcloud run jobs create YOUR_IMAGE-job --image gcr.io/YOUR_PROJECT/YOUR_IMAGE:latest
   ```

5. Set up the Cloud Scheduler job to trigger this.

Be mindful of permissions and ensure your GCP project is set up correctly. Check `index.md` for more details and troubleshooting tips.
