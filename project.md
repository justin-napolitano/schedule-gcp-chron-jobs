---
slug: github-schedule-gcp-chron-jobs
id: github-schedule-gcp-chron-jobs
title: Scheduling Jobs on Google Cloud Run with Cloud Scheduler
repo: justin-napolitano/schedule-gcp-chron-jobs
githubUrl: https://github.com/justin-napolitano/schedule-gcp-chron-jobs
generatedAt: '2025-11-24T21:36:16.014Z'
source: github-auto
summary: >-
  Learn how to automate job scheduling on Google Cloud Run using Google Cloud
  Scheduler and Docker.
tags:
  - docker
  - python
  - gcloud
  - pubsub
seoPrimaryKeyword: google cloud run job scheduling
seoSecondaryKeywords:
  - cloud scheduler setup
  - dockerize python script
  - gcloud cli commands
  - automate container workloads
  - google cloud automation
seoOptimized: true
topicFamily: null
topicFamilyConfidence: null
kind: project
entryLayout: project
showInProjects: true
showInNotes: false
showInWriting: false
showInLogs: false
---

A practical guide and example for scheduling jobs on Google Cloud Run using Google Cloud Scheduler. This repository demonstrates how to automate running containerized workloads at regular intervals, such as hourly executions, leveraging GCP's managed services.

---

## Features

- Sample Dockerfile for containerizing a Python script
- Commands to build and push Docker images to Google Container Registry
- Instructions to create and deploy Cloud Run jobs
- Setup for scheduling Cloud Run jobs with Google Cloud Scheduler

## Tech Stack

- Google Cloud Platform (Cloud Run, Cloud Scheduler, Container Registry)
- Docker
- Python (example script)
- Bash (CLI commands)

## Getting Started

### Prerequisites

- Google Cloud project with billing enabled
- `gcloud` CLI installed and authenticated
- Permissions to create Cloud Run jobs and Cloud Scheduler jobs
- Docker installed locally or use Cloud Build

### Installation and Usage

1. Clone the repository:

```bash
git clone https://github.com/justin-napolitano/schedule-gcp-chron-jobs.git
cd schedule-gcp-chron-jobs
```

2. Prepare your Python script (`script.py`) or replace it with your workload.

3. Build and push the Docker image:

```bash
PROJECT_NAME="your-project-name"
IMAGE_NAME="your-image-name"
TAG="latest"
REGION="us-west2"

gcloud builds submit --tag gcr.io/$PROJECT_NAME/$IMAGE_NAME:$TAG
```

4. Create the Cloud Run job:

```bash
gcloud run jobs create $IMAGE_NAME-job \
    --image gcr.io/$PROJECT_NAME/$IMAGE_NAME:$TAG \
    --region $REGION
```

5. Schedule the job using Cloud Scheduler (example for hourly execution):

```bash
SCHEDULER_NAME="$IMAGE_NAME-scheduler"

# Create scheduler job to trigger Cloud Run job
# (This requires setting up a Pub/Sub topic or HTTP trigger depending on your setup)

# Example placeholder command:
# gcloud scheduler jobs create pubsub $SCHEDULER_NAME --schedule="0 * * * *" --topic=your-topic --message-body="Trigger"
```

Refer to GCP documentation to configure the exact trigger mechanism.

## Project Structure

```
index.md          # Tutorial and documentation on scheduling Cloud Run jobs
Dockerfile        # Example Dockerfile to containerize Python script
script.py         # Example Python script (assumed)
README.md         # This file
```

## Future Work / Roadmap

- Add complete example scripts and Dockerfile in the repo
- Provide automated deployment scripts
- Include examples for different scheduling intervals and triggers
- Add support for monitoring and logging scheduled job executions
- Enhance documentation with troubleshooting tips

---

For detailed instructions, see the tutorial in `index.md`.

