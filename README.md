# 🩺 MedAssist AI — Clinical Symptom Screening & Healthcare Platform

### Intelligent Disease Prediction, Risk Assessment & Full-Stack Clinical Management Platform

[![Live Demo](https://img.shields.io/badge/Live%20Demo-medassistai--frontend.vercel.app-brightgreen.svg?style=for-the-badge&logo=vercel)](https://medassistai-frontend.vercel.app)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688.svg?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![React 19](https://img.shields.io/badge/Frontend-React%2019-61DAFB.svg?style=for-the-badge&logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Build-Vite-646CFF.svg?style=for-the-badge&logo=vite)](https://vitejs.dev/)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-3776AB.svg?style=for-the-badge&logo=python)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/ML-Scikit--Learn-F7931E.svg?style=for-the-badge&logo=scikitlearn)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/ML-XGBoost-189FDD.svg?style=for-the-badge&logo=xgboost)](https://xgboost.ai/)
[![LightGBM](https://img.shields.io/badge/ML-LightGBM-9ACD32.svg?style=for-the-badge&logo=lightgbm)](https://lightgbm.readthedocs.io/)
[![Docker](https://img.shields.io/badge/Container-Docker-2496ED.svg?style=for-the-badge&logo=docker)](https://www.docker.com/)

---

## 📌 Project Overview

**MedAssist AI** is an end-to-end, AI-powered healthcare platform designed to assist patients, doctors, and administrative staff through intelligent symptom screening, probabilistic disease prediction, clinical risk assessment, medical recommendations, appointments, and report management.

Built as a modern full-stack application, MedAssist AI features a high-performance **FastAPI + Machine Learning** backend paired with a responsive, interactive **React 19 + Vite** frontend. The platform uses an ensemble **Voting Classifier (Random Forest + XGBoost + LightGBM)** trained on clinical datasets to accurately map user-reported symptoms to potential medical conditions with associated risk metrics.

---

## 🌐 Live Deployment

MedAssist AI is fully deployed and accessible live:

- **🚀 Live Web Application**: [https://medassistai-frontend.vercel.app](https://medassistai-frontend.vercel.app) *(Deployed on Vercel)*
- **⚡ Backend REST API**: Configured via Render with automatic model fetching from Hugging Face.
- **📖 Interactive API Docs**: Access Swagger docs at `http://127.0.0.1:8000/docs` locally or via the deployed API backend.

---

## 🌟 Key Features

### 🧠 1. AI Symptom Screening & Decision Engine
- **Multi-Symptom Input**: Interactive symptom selection and search across comprehensive medical symptom dictionaries.
- **Ensemble ML Voting Classifier**: Combines predictions from **Random Forest**, **XGBoost**, and **LightGBM** models for robust diagnostic inference.
- **3-Tier Clinical Analysis Engine**:
  - **Disease Prediction**: Answers *"What condition might I have?"* with probabilistic confidence scores and disease mapping.
  - **Risk Assessment**: Answers *"How serious is it?"* with risk level tiers (Low, Moderate, High, Critical), severity scores, and emergency flags.
  - **Medical Recommendations**: Answers *"What should I do next?"* with actionable guidance, monitoring steps, self-care routines, and emergency escalation triggers.

### 👨‍⚕️ 2. Role-Based Portals & Dashboards
- **Patient Portal**: Personalized health dashboard, symptom checker, diagnostic history, medical report downloads, appointment scheduling, and prescription history.
- **Doctor Portal**: Assigned patient management, real-time appointment tracking, clinical note authoring, prescription creation, and disease distribution analytics.
- **Admin Portal**: System-wide analytics, doctor & patient management, appointment status oversight, and system settings.

### 📋 3. Clinical Health Reports & History
- Automated report generation containing patient details, symptom inputs, predicted conditions, risk gauge indicators, severity metrics, and clinical recommendations.
- Doctor notes integration and printable/downloadable health report support.

### 🔒 4. Authentication & Security
- Secure **JWT Bearer Token** authentication with Bcrypt password hashing.
- Role-Based Access Control (RBAC) enforcing strict permission boundaries across endpoints and frontend routes.

---

## 🧠 Disease Prediction & ML Pipeline

The disease prediction system follows an end-to-end machine learning and clinical assessment workflow:

```text
                User Symptom Selection
                          │
                          ▼
             Symptom Validation & Search
                          │
                          ▼
            Feature Extraction & Encoding
                          │
                          ▼
        Ensemble Voting Classifier Model
      ┌───────────────────┼───────────────────┐
      ▼                   ▼                   ▼
Random Forest         XGBoost             LightGBM
      └───────────────────┬───────────────────┘
                          │
                          ▼
         Disease Prediction & Probability Score
                          │
                          ▼
              Medical Disease Name Mapping
                          │
                          ▼
                Health Risk Assessment
                          │
                          ▼
                 Clinical Severity Metrics
                          │
                          ▼
              Actionable Recommendations
                          │
                          ▼
          Clinical Health Report Generation
```

### ML Pipeline Highlights:
- **Datasets**: Preprocessed and weighted clinical datasets (`clean_190k_dataset.csv`, `final_dataset.csv`, `weighted_final_dataset.csv`).
- **Model Loader**: Dynamic model initialization supporting local weights as well as Hugging Face remote model retrieval for lightweight cloud deployments.
- **Startup Lazy-Loading**: Preloads model artifacts during application startup for zero-latency inference on incoming API requests.

---

## 🛠️ Technology Stack

| Layer | Technology | Description |
|---|---|---|
| **Frontend** | **React 19**, **Vite** | Modern, lightning-fast UI client |
| **Styling & Components** | **Tailwind CSS**, Lucide Icons | Responsive, glassmorphic design system |
| **Routing & Client** | React Router v7, Axios | Single Page App navigation & API client |
| **Backend Framework** | **FastAPI**, **Uvicorn** | High-performance Python REST API |
| **Machine Learning** | **Scikit-Learn**, **XGBoost**, **LightGBM** | Ensemble ML model voting classifier |
| **Model Serialization** | Joblib, NumPy, Pandas | ML model pipeline and data processing |
| **Database & ORM** | **PostgreSQL** / **SQLite**, **SQLAlchemy** | Relational database storage & ORM mapping |
| **Validation & Security** | Pydantic v2, PyJWT, Passlib (Bcrypt) | Data validation & secure token authentication |
| **Containerization** | **Docker**, Docker Compose | Multi-container setup for seamless deployment |
| **Deployment** | **Vercel** (Frontend), **Render** (Backend) | Cloud hosting and CI/CD integration |

---

## 📂 Repository Architecture

```text
MedAssist-AI/
├── backend/                      # Production Backend Application
│   ├── app/
│   │   ├── config/              # Application settings & environment configuration
│   │   ├── database/            # SQLAlchemy database engine, session, & seed scripts
│   │   ├── ml/                  # ML model (lgb_model.pkl), predictor, preprocessing, disease mapping
│   │   ├── models/              # Database models (User, Patient, Doctor, Appointment, Prescription, etc.)
│   │   ├── routers/             # FastAPI route handlers (Auth, Patient, Doctor, Appointment, Prescription, Predict, Reports, Analytics)
│   │   ├── schemas/             # Pydantic validation & response schemas
│   │   ├── services/            # Business logic, analysis, & recommendation engines
│   │   ├── utils/               # JWT security, password hashing, & permission guards
│   │   └── main.py              # FastAPI application entrypoint
│   ├── .dockerignore
│   ├── .env.example             # Backend environment variable template
│   ├── .gitignore
│   ├── Dockerfile               # Container build instructions
│   ├── docker-compose.yml       # Docker compose orchestration
│   ├── render.yaml              # Cloud deployment specification
│   ├── requirements.txt         # Python package dependencies
│   ├── test_all_endpoints.py    # Test suite for API endpoints
│   ├── test_audit_suite.py      # System security & audit verification
│   ├── test_doctor_creation.py  # Doctor onboarding tests
│   ├── test_full_system.py      # End-to-end integration test suite
│   └── test_multi_symptoms.py   # Multi-symptom inference test suite
│
├── frontend/                     # Production Frontend Application
│   ├── public/                  # Static assets & public files
│   ├── src/
│   │   ├── assets/              # Static media & artwork
│   │   ├── components/          # Reusable UI components
│   │   │   ├── analytics/       # Analytics charts & metric cards
│   │   │   ├── auth/            # ProtectedRoute & auth components
│   │   │   ├── landing/         # Modern landing page sections (Hero, Story, Expertise, Studios, Feedback, etc.)
│   │   │   ├── layout/          # DashboardLayout, Sidebar, TopBar
│   │   │   ├── prediction/      # Prediction results display
│   │   │   ├── recommendations/ # Clinical guidance cards
│   │   │   ├── reports/         # Report viewer & download handlers
│   │   │   ├── risk/            # Risk gauges & severity indicators
│   │   │   ├── symptoms/        # Interactive symptom selector & search
│   │   │   └── ui/              # Button, Card, Input, Modal, ThemeToggle, ErrorBoundary
│   │   ├── constants/           # User roles (ADMIN, DOCTOR, PATIENT) & app constants
│   │   ├── context/             # React Context (AuthContext, SessionContext, ThemeContext)
│   │   ├── hooks/               # Custom React hooks (useAuth, useSymptomChecker, useReportDownload)
│   │   ├── pages/               # Application views & dashboards
│   │   │   ├── auth/            # LoginPage, RegisterPage
│   │   │   ├── dashboard/       # Role-specific portals (Admin, Doctor, Patient)
│   │   │   └── landing/         # LandingPage
│   │   ├── routes/              # AppRoutes configuration
│   │   ├── services/            # Axios API integration clients & mock services
│   │   ├── styles/              # Global CSS & Tailwind design tokens
│   │   ├── App.jsx              # Main React application component
│   │   ├── index.css            # Global styling
│   │   └── main.jsx             # React entry point
│   ├── .env.example             # Frontend environment variable template
│   ├── .gitignore
│   ├── package.json             # Frontend dependencies & npm scripts
│   ├── package-lock.json
│   ├── tailwind.config.js       # Tailwind CSS styling configuration
│   ├── vercel.json              # Vercel deployment routing configuration
│   └── vite.config.js           # Vite build configuration
│
├── .gitignore                    # Root Git ignore rules
├── LICENSE                       # MIT License
└── README.md                     # Main Project Documentation
```

---

## 🔌 API Endpoints Reference

### 🔐 Authentication (`/auth`)
| Method | Endpoint | Description | Access |
|---|---|---|---|
| `POST` | `/auth/register` | Register a new user (Patient/Doctor/Admin) | Public |
| `POST` | `/auth/login` | Authenticate user and receive JWT access token | Public |
| `GET` | `/auth/me` | Retrieve authenticated user profile | Authenticated |

### 🧠 Disease Prediction & Screening (`/predict`, `/symptoms`)
| Method | Endpoint | Description | Access |
|---|---|---|---|
| `GET` | `/symptoms` | Get list of supported symptoms | Public |
| `POST` | `/predict` | Run symptom list through ML pipeline for prediction & risk | Authenticated |

### 👤 Patient & Doctor Portals (`/patient`, `/doctor`)
| Method | Endpoint | Description | Access |
|---|---|---|---|
| `GET` | `/patient/profile` | Get patient medical profile | Patient |
| `PUT` | `/patient/profile` | Update patient medical profile | Patient |
| `GET` | `/doctor/profile` | Get doctor profile & availability | Doctor |
| `PUT` | `/doctor/profile` | Update doctor profile & schedules | Doctor |

### 📅 Appointments & Prescriptions (`/appointments`, `/prescriptions`)
| Method | Endpoint | Description | Access |
|---|---|---|---|
| `POST` | `/appointments` | Schedule a medical appointment | Patient |
| `GET` | `/appointments/my` | Retrieve user's appointment history | Authenticated |
| `PUT` | `/appointments/{id}/status` | Update appointment status (Confirmed/Cancelled) | Doctor / Admin |
| `POST` | `/prescriptions` | Create a new prescription for patient | Doctor |

### 📋 Health Reports & Analytics (`/reports`, `/analytics`)
| Method | Endpoint | Description | Access |
|---|---|---|---|
| `GET` | `/reports/my` | Get diagnostic report history | Patient |
| `GET` | `/reports/{id}` | Get detailed health report | Authenticated |
| `PUT` | `/reports/{id}/notes` | Add clinical notes to health report | Doctor |
| `GET` | `/analytics/summary` | Get platform usage & overview metrics | Admin / Doctor |
| `GET` | `/analytics/diseases` | Get disease prediction distribution statistics | Admin / Doctor |

---

## 🚀 Quick Start Guide

### Prerequisites
- **Node.js**: v18.0 or higher
- **Python**: v3.10 or higher
- **Git**

---

### 1. Clone the Repository

Clone your repository to get started:

```bash
git clone https://github.com/sanvisawant/MedAssist-AI.git
cd MedAssist-AI
```

---

### 2. Backend Setup & Run

Open a terminal and set up the FastAPI backend:

```bash
# Navigate to the backend directory
cd backend

# Create a Python virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows (PowerShell):
venv\Scripts\Activate.ps1
# On Windows (Command Prompt):
venv\Scripts\activate.bat
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Start the FastAPI server
python -m uvicorn app.main:app --reload --host 127.0.0.1 --port 8000
```

- **Backend Server**: `http://127.0.0.1:8000`
- **Interactive Swagger Docs**: `http://127.0.0.1:8000/docs`

---

### 3. Frontend Setup & Run

Open a separate terminal window and start the React client:

```bash
# Navigate to the frontend directory
cd frontend

# Install Node dependencies
npm install

# Start Vite development server
npm run dev
```

- **Frontend Application**: `http://localhost:5173`

---

### 4. Docker Setup (Optional)

To build and run the backend using Docker Compose:

```bash
# Navigate to backend directory
cd backend

# Run with Docker Compose
docker-compose up --build -d
```

---

## ⚙️ Environment Configuration

Environment configuration is managed via `.env.example` templates committed in each respective project folder:

- **Backend Environment**: Copy `backend/.env.example` ➔ `backend/.env`
- **Frontend Environment**: Copy `frontend/.env.example` ➔ `frontend/.env`

*(Refer to `.env.example` inside `backend/` and `frontend/` for available environment variable keys and defaults.)*

---

## 📄 License

This project is licensed under the **MIT License**. See the [`LICENSE`](LICENSE) file for more details.

---

## 👥 Contributors

- **Sanvi Sawant**

---
*For questions, issues, or contributions, please feel free to submit an issue or pull request on the [GitHub repository](https://github.com/sanvisawant/MedAssist-AI).*
