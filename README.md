# Tenadam Digital Healthcare System

**TENADAM** is an integrated digital healthcare platform designed to improve healthcare accessibility, coordination, interoperability, and efficiency across urban and rural communities.

The platform brings together hospital management, telemedicine, pharmacy management, emergency healthcare, AI-assisted services, USSD access, healthcare interoperability, and administrative management into a unified digital health ecosystem.

---

## 🏗️ Architecture

Tenadam is a modular, multi-tenant healthcare platform built using modern technologies.

| Layer | Technology |
|---|---|
| Backend | Go (Golang) Microservices |
| AI Services | Python + FastAPI |
| Web Frontend | Next.js 14 + TypeScript |
| Mobile | Capacitor |
| Database | PostgreSQL |
| Cache | Redis |
| Message Bus | Apache Kafka |
| Video & Telemedicine | LiveKit |
| Interoperability | FHIR R4 |
| Containers | Docker |
| Orchestration | Kubernetes |

---

## 📁 Project Structure

```text
Tenadam-Digital-Health-Platform/
│
├── apps/
│   ├── web/                    # Next.js web applications
│   ├── mobile/                 # Capacitor mobile application
│   └── ussd/                   # USSD application
│
├── backend/                    # Backend support and shared backend code
│
├── gateway/
│   └── api-gateway/            # Central API Gateway
│
├── services/
│   ├── core/                   # Authentication, users, access control
│   ├── registry/               # Patients, practitioners, facilities
│   ├── clinical/               # Clinical and patient-care services
│   ├── clinical-extensions/    # Forms, orders, guidelines, terminology
│   ├── diagnostics/            # Laboratory and diagnostic services
│   ├── pharmacy/               # Pharmacy, prescriptions, inventory
│   ├── hospital/               # Hospital and inpatient management
│   ├── emergency/              # Emergency, triage and ambulance
│   ├── surgery/                # Surgery and theatre management
│   ├── operations/             # Appointments, scheduling and queues
│   ├── financial/              # Billing, payments and insurance
│   ├── supply-chain/           # Procurement, vendors and warehouse
│   ├── ai/                     # AI healthcare services
│   ├── telemedicine/           # Video consultation and remote care
│   ├── communication/          # Notifications, messaging and USSD
│   ├── integration/            # FHIR and interoperability
│   ├── analytics/              # Reporting and dashboards
│   └── public-health/          # Surveillance and public health
│
├── packages/                   # Shared packages and utilities
│
├── database/
│   ├── migrations/             # Database migrations
│   ├── seeds/                  # Development and demonstration data
│   └── schemas/                # Database schemas
│
├── infrastructure/             # Docker, Kubernetes and deployment
├── docs/                       # Project documentation
├── tools/                      # Development and administration tools
│
├── docker-compose.yml
├── Makefile
├── .env.example
├── LICENSE
└── README.md
```

---

## ✨ Key Features

### 🏥 Hospital Management

- Patient registration and management
- Healthcare organization and facility management
- Staff and role management
- Appointment and scheduling
- Ward and bed management
- Inpatient management
- Clinical records and documentation
- Hospital administration

### 💊 Pharmacy Management

- Medication management
- Electronic prescriptions
- Prescription processing
- Medication dispensing
- Pharmacy inventory management
- Stock monitoring
- Expiry tracking
- Pharmacy administration

### 📹 Telemedicine

- Doctor-patient video consultation
- Real-time patient communication
- Secure video sessions
- LiveKit integration
- Remote healthcare services
- Telemedicine scheduling
- Remote patient access

### 🚑 Emergency Healthcare

- Emergency management
- Patient triage
- ICU management
- Ambulance coordination
- Emergency response workflows
- Critical-care support

### 🤖 AI-Powered Healthcare

- AI-assisted patient triage
- Diagnosis support
- Clinical decision support
- Patient risk prediction
- Clinical text processing
- Natural Language Processing
- Population health analytics
- AI-assisted auditing

### 📱 Rural & Low-Connectivity Healthcare

- USSD healthcare services
- Voice and IVR support
- Community healthcare access
- Rural healthcare support
- Accessibility-focused services
- Local-language support

### 🔗 Healthcare Interoperability

- FHIR R4 support
- EMR interoperability
- Standardized healthcare data exchange
- Patient data integration
- Clinical information exchange
- External healthcare system integration

---

## 🚀 Getting Started

### Prerequisites

Make sure the following are installed:

- **Git**
- **Go 1.22+**
- **Node.js 20+**
- **npm**
- **Docker Desktop**
- **Docker Compose**
- **PostgreSQL** (optional when using Docker)
- **kubectl** (required only for Kubernetes deployment)

---

## 📥 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Firaolfro/Tenadam-Digital-Health-Platform.git
cd Tenadam-Digital-Health-Platform
```

### 2. Configure Environment Variables

Copy the example environment file.

#### Windows

```cmd
copy .env.example .env
```

#### Linux / macOS

```bash
cp .env.example .env
```

Open `.env` and configure the required values.

> ⚠️ Never commit `.env`, production environment files, passwords, API keys, JWT secrets, or other sensitive credentials.

---

## 🐳 Running with Docker

Docker is the recommended way to start the Tenadam infrastructure.

### Start the System

```bash
docker compose up -d
```

### Check Running Containers

```bash
docker compose ps
```

### View Logs

```bash
docker compose logs -f
```

### Stop the System

```bash
docker compose down
```

### Restart the System

```bash
docker compose restart
```

---

## 🗄️ Database

Tenadam uses **PostgreSQL** as its primary database.

Database files are organized under:

```text
database/
├── migrations/
├── seeds/
└── schemas/
```

Run the project's database migration command:

```bash
make migrate
```

Check the database-related containers:

```bash
docker compose ps
```

---

## 🌐 Running the Web Application

Navigate to the web application:

```bash
cd apps/web
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The web application will normally be available at:

```text
http://localhost:3000
```

Open the address in your browser.

---

## 🔧 Running Backend Services

Tenadam uses Go-based microservices.

For example, to run the authentication service:

```bash
cd services/core/auth-service
go run ./cmd/main.go
```

Individual services can be started independently depending on the development requirement.

---

## ▶️ Starting the Full System on Windows

The repository includes Windows batch scripts for easier development.

From the project root:

```cmd
start-full-system.bat
```

or:

```cmd
start-system.bat
```

These scripts can be used to start the required components of the system.

---

## 🛠️ Useful Development Commands

### Build All Services

```bash
make build-all
```

### Run Go Tests

```bash
make test-go
```

### Run Web Tests

```bash
make test-web
```

### Run Development Infrastructure

```bash
make dev
```

### Run Database Migrations

```bash
make migrate
```

---

## 📹 Telemedicine & LiveKit

Tenadam uses **LiveKit** for real-time video communication and telemedicine sessions.

Configure the LiveKit environment variables in `.env`:

```env
LIVEKIT_API_KEY=<your_livekit_api_key>
LIVEKIT_API_SECRET=<your_livekit_api_secret>
LIVEKIT_PUBLIC_URL=wss://<your-project>.livekit.cloud
```

Restart the API gateway after changing the configuration:

```bash
docker compose up -d api-gateway
```

Verify the gateway environment:

```bash
docker compose ps
```

For remote telemedicine testing, both users should connect through the configured LiveKit server.

---

## 🔐 Security

Tenadam is designed with security and healthcare data protection in mind.

Security mechanisms include:

- JWT-based authentication
- Role-based access control
- Multi-tenant data isolation
- API gateway security
- Audit logging
- Secure environment configuration
- Encrypted communication
- Healthcare data protection
- Access control and authorization
- Secure service-to-service communication

### Never Commit Sensitive Information

Do not commit:

```text
.env
.env.local
.env.production
API keys
JWT secrets
Database passwords
Private certificates
Production credentials
```

The repository `.gitignore` is configured to prevent sensitive files from being committed.

---

## 🏢 Multi-Tenancy

Tenadam is designed as a **multi-tenant digital healthcare platform**.

Healthcare organizations, facilities, users, and resources can be isolated using tenant-level access control.

Authentication and authorization are handled through the core authentication services and API gateway.

This architecture allows multiple healthcare organizations to operate securely within the same platform.

---

## 🤖 AI Services

AI services are implemented using **Python and FastAPI**.

The platform architecture supports:

- AI Triage
- Diagnosis Support
- Clinical Decision Support
- Risk Prediction
- Clinical NLP
- Population Health Analytics
- AI Audit Analysis
- Healthcare Policy Compliance

AI services are designed to assist healthcare professionals and improve healthcare decision-making.

---

## 📱 Mobile Application

The Tenadam mobile architecture uses **Capacitor** to provide a native mobile experience based on the web application.

The architecture supports deployment to:

- Android
- iOS

This allows Tenadam to extend healthcare services beyond desktop and web environments.

---

## 📞 USSD & Voice Services

Tenadam supports healthcare access for users with limited internet connectivity.

The platform architecture includes:

- USSD services
- Voice / IVR services
- Community healthcare access
- Rural healthcare support
- Low-bandwidth healthcare services

This approach helps extend digital healthcare services to communities where smartphones, mobile data, or reliable internet connectivity may be limited.

---

## 🧩 Microservice Architecture

Each Go microservice follows a consistent structure:

```text
service-name/
├── cmd/
│   └── main.go
├── api/
│   └── routes.go
├── internal/
│   ├── handler/
│   ├── service/
│   ├── repository/
│   ├── model/
│   ├── dto/
│   ├── middleware/
│   └── events/
├── migrations/
├── Dockerfile
└── go.mod
```

The architecture separates:

- API handling
- Business logic
- Data access
- Domain models
- Request/response DTOs
- Middleware
- Event processing

This improves maintainability, scalability, testing, and service independence.

---

## 🔗 FHIR Integration

Tenadam supports healthcare interoperability using **FHIR R4**.

FHIR enables standardized healthcare information exchange between Tenadam and external healthcare systems.

Supported healthcare information can include:

- Patients
- Practitioners
- Organizations
- Encounters
- Observations
- Medications
- Medication Requests
- Procedures
- Diagnostic results

---

## 🧪 Development Workflow

A typical development workflow is:

1. Clone the repository.
2. Configure environment variables.
3. Start Docker infrastructure.
4. Run database migrations.
5. Install frontend dependencies.
6. Start the required backend services.
7. Start the web application.
8. Test the required modules.
9. Create a feature branch for changes.
10. Commit and push changes.

Create a feature branch:

```bash
git checkout -b feature/your-feature-name
```

Check project status:

```bash
git status
```

Commit changes:

```bash
git add .
git commit -m "feat: describe your change"
```

Push the branch:

```bash
git push -u origin feature/your-feature-name
```

---

## 📚 Documentation

Additional project documentation is available throughout the repository.

Important documentation includes:

- `COMPLETE_GUIDE.md`
- `COMPREHENSIVE_TESTING_GUIDE.md`
- `DATABASE_DEPLOYMENT_GUIDE.md`
- `DATABASE_IMPLEMENTATION_CHECKLIST.md`
- `DOCUMENTATION_INDEX.md`
- `GITHUB_SETUP.md`
- `NATIONAL_PHARMACY_SYSTEM_DESIGN.md`
- `PHARMACY_SYSTEM_DESIGN.md`
- `PROJECT_TODO_LIST.md`
- `VISUAL_DEPLOYMENT_GUIDE.md`
- Staff management documentation
- Telemedicine documentation
- Database documentation
- Deployment documentation

Additional documentation is also available inside the `docs/` directory.

---

## 🤝 Contributing

Contributions and improvements are welcome.

Before submitting changes:

1. Create a feature branch.
2. Follow the existing project structure.
3. Write or update tests where necessary.
4. Keep documentation updated.
5. Do not commit secrets or environment files.
6. Verify the application before submitting changes.
7. Use clear and descriptive commit messages.

---

## 📄 License

This project is licensed under the **MIT License**.

See the [`LICENSE`](./LICENSE) file for details.

---

## 🎓 Project

**Tenadam Digital Healthcare System**

An integrated digital health platform focused on improving healthcare accessibility, interoperability, coordination, and service delivery through modern software technologies.

### Repository

https://github.com/Firaolfro/Tenadam-Digital-Health-Platform

---

## ⭐ Project Highlights

**Tenadam brings together:**

🏥 Hospital Management  
💊 Pharmacy Management  
📹 Telemedicine  
🚑 Emergency Healthcare  
🤖 AI-Assisted Healthcare  
📱 Mobile Healthcare  
📞 USSD & Voice Services  
🔗 FHIR Interoperability  
🏢 Multi-Tenant Architecture  
🔐 Secure Healthcare Data Management  
🐳 Docker-Based Deployment  
☸️ Kubernetes-Ready Infrastructure

---

**Built as a modern digital healthcare platform for scalable and accessible healthcare delivery.**
