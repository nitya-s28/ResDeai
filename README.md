# ResDe.ai Clinical Appointment Dashboard

## Overview

This project is a Clinical Appointment Dashboard built using Next.js, React, Tailwind CSS, and Firebase Firestore.

The dashboard allows clinicians to:

- View patient information
- Track appointment status
- Access medical reports
- Search patient records



## Tech Stack

- Next.js
- React
- TypeScript
- Tailwind CSS
- Firebase Firestore



## Features

### Frontend

- Responsive dashboard UI
- Search functionality
- Appointment status indicators
- Reusable React components
- Real-time Firestore updates

### Backend / Data

- Firestore NoSQL database
- Patient record schema
- Embedded appointment and report arrays

### Security

- Role-based access logic for clinical notes
- Audit logging for patient record access



## Firestore Schema

Each patient document contains:

- Personal Information
- Appointments array
- Reports array
  
---


## Authentication & Authorization

For simplicity, authentication was mocked using a predefined doctor role.

In production, Firebase Authentication and JWT-based role verification would be implemented.

Only users with role `DOCTOR` can access clinical notes.



## Audit Logging

Audit logs are generated whenever patient records are accessed.

Each log stores:

- patientId
- accessedBy
- timestamp

---

## Cloud Deployment Strategy

## Deployment Strategy: Google Cloud Run + Firestore

### Google Cloud Run

The Next.js application would be containerized using Docker and deployed on Google Cloud Run.

Cloud Run provides:

- Serverless deployment
- Automatic scaling
- HTTPS endpoints
- High availability
- Zero-downtime rollbacks using revisions

Environment variables and Firebase credentials would be securely managed through Cloud Run service settings instead of being exposed in source code.

### Google Cloud Firestore

Firestore is used as a scalable NoSQL database for storing patient records, appointments, and reports.

The database structure uses:

- A main `Patients` collection
- Embedded appointment and report data
- Real-time synchronization support

Firestore Security Rules would restrict sensitive healthcare data access to authorized users only.



## CI/CD Pipeline with Liveness Check

A GitHub Actions pipeline would automatically run whenever a Pull Request targets the production branch.

### Pipeline Steps

1. Install dependencies using `npm ci`
2. Run linting and TypeScript checks
3. Build the Next.js application
4. Build and validate the Docker image
5. Deploy to a temporary staging environment
6. Run a liveness check on `/api/health`

The liveness check verifies:

- Successful application startup
- Firestore connectivity
- Healthy API response



### Empathy-Based Error Message

Instead of:

`Error 404: Patient Not Found`

Use:

> We couldn’t find this patient record right now.  
> Don’t worry — sometimes records take a moment to appear or may be under a different ID.  
> You can try searching again, or quickly create a new record if needed.  
> We’re here to help you keep moving smoothly.



## Running Locally

```bash
npm install
npm run dev
```
---


## Future Improvements

- Firebase Authentication
- Advanced RBAC permissions
- Appointment scheduling
- Report uploads
- Cloud monitoring and analytics

  ---

  ---

## Screenshots

### Dashboard UI

![Dashboard](./screenshots/dashboard.png)

---

### Firestore Database Structure

![Firestore](./screenshots/firestore.png)

---

### Project Structure

![Project Structure](./screenshots/1p.png)
![Project Structure](./screenshots/2p.png)
![Project Structure](./screenshots/3p.png)
![Project Structure](./screenshots/4p.png)
![Project Structure](./screenshots/5p.png)
![Project Structure](./screenshots/6p.png)
![Project Structure](./screenshots/7p.png)
![Project Structure](./screenshots/8p.png)
![Project Structure](./screenshots/9p.png)
![Project Structure](./screenshots/10p.png)
