# ResDe.ai Clinical Appointment Dashboard

## Overview

This project is a Clinical Appointment Dashboard built using Next.js, React, Tailwind CSS, and Firebase Firestore.

The dashboard allows clinicians to:

- View patient information
- Track appointment status
- Access medical reports
- Search patient records
- 
## AI-Assisted Development

This project was intentionally developed using an AI-assisted engineering workflow to simulate agentic software development practices, including rapid scaffolding, debugging, architectural refinement, and iterative production-grade corrections.


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

<img width="1227" height="906" alt="Screenshot 2026-05-20 131751" src="https://github.com/user-attachments/assets/8c4a2925-3aaa-40bb-8dac-e703f72bd5d3" />



---

### Firestore Database Structure
<img width="1305" height="746" alt="firestore png" src="https://github.com/user-attachments/assets/c0526cd5-ea41-410c-a3b5-93718b360403" />


---

### Project Structure

<img width="237" height="906" alt="1p" src="https://github.com/user-attachments/assets/dbb68640-5877-48a0-9af2-d65d651828c4" />
<img width="703" height="952" alt="2p" src="https://github.com/user-attachments/assets/1519f923-fd13-425a-a61f-1282c04de6ee" />
<img width="983" height="930" alt="3p" src="https://github.com/user-attachments/assets/2e3d291d-116b-4ee6-9334-eb3a807bb40b" />
<img width="917" height="658" alt="4p" src="https://github.com/user-attachments/assets/8c013522-b16e-4b6b-8230-61422c9b90fb" />
<img width="875" height="656" alt="5p" src="https://github.com/user-attachments/assets/14db6938-88bc-4426-9cad-2dbc54df96f4" />
<img width="897" height="692" alt="6p" src="https://github.com/user-attachments/assets/ae421403-8d9f-47e7-a81b-1fdf4562e8e0" />
<img width="585" height="490" alt="7p" src="https://github.com/user-attachments/assets/21174e4d-aec3-4cef-a6e4-0111745dccea" />
<img width="447" height="298" alt="8p" src="https://github.com/user-attachments/assets/be84a8c9-83e5-4b4b-a381-350c99357f95" />
<img width="428" height="327" alt="9p" src="https://github.com/user-attachments/assets/1ee32310-6bbf-49c7-9c92-209bda32c8d7" />
<img width="512" height="336" alt="10p" src="https://github.com/user-attachments/assets/7a8b4316-515b-4bcd-8a79-0a2f5d0eca36" />

---

## Deployment Status

The application was prepared for deployment using Vercel / Netlify and Google Cloud Run architecture principles.

Due to authentication constraints during submission, the final hosted deployment was not completed.

However, the project runs successfully in the local development environment using:

```bash
npm run dev
```

The application was fully tested locally with Firebase Firestore integration enabled.

