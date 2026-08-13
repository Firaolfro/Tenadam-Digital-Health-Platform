# Tenadam Digital Healthcare System

TENADAM is an integrated digital healthcare platform designed to improve healthcare accessibility, coordination, and efficiency across urban and rural communities.

The platform combines hospital management, telemedicine, pharmacy management, emergency services, AI-assisted healthcare, USSD access, and healthcare interoperability into a unified digital health ecosystem.

---

## 🏗 Architecture

Tenadam is a modular, multi-tenant monorepo built with modern technologies:

| Layer | Technology |
|---|---|
| Backend | Go (Golang) Microservices |
| AI Services | Python + FastAPI |
| Web | Next.js 14 + TypeScript |
| Mobile | Capacitor |
| Database | PostgreSQL |
| Cache | Redis |
| Message Bus | Apache Kafka |
| Video | LiveKit |
| Interoperability | FHIR |
| Deployment | Docker + Kubernetes |

---

## 📁 Project Structure

```text
Tenadam-Digital-Health-Platform/
│
├── apps/
│   ├── web/                 # Next.js web applications
│   ├── mobile/              # Capacitor mobile application
│   └── ussd/                # USSD application
│
├── backend/                 # Backend support and shared backend code
├── gateway/
│   └── api-gateway/         # Central API Gateway
│
├── services/
│   ├── core/                # Authentication, users, access control
│   ├── registry/            # Patients, practitioners, facilities
│   ├── clinical/            # Clinical and patient-care services
│   ├── diagnostics/        # Laboratory and diagnostic services
│   ├── pharmacy/            # Pharmacy, prescriptions, inventory
│   ├── hospital/            # Hospital and inpatient management
│   ├── emergency/           # Emergency and ambulance services
│   ├── surgery/             # Surgery and theatre management
│   ├── operations/          # Appointment, scheduling and queue
│   ├── financial/           # Billing, payments and insurance
│   ├── supply-chain/        # Procurement and warehouse
│   ├── ai/                  # AI healthcare services
│   ├── telemedicine/        # Video consultation and remote care
│   ├── communication/       # Notifications, messaging and USSD
│   ├── integration/         # FHIR and interoperability
│   ├── analytics/           # Reporting and dashboards
│   └── public-health/       # Public health and surveillance
│
├── packages/                # Shared packages and utilities
├── database/
│   ├── migrations/          # Database migrations
│   ├── seeds/               # Development/demo data
│   └── schemas/             # Database schemas
│
├── infrastructure/          # Docker, Kubernetes and deployment
├── docs/                    # Project documentation
├── tools/                   # Development and administration tools
│
├── docker-compose.yml
├── Makefile
├── .env.example
├── LICENSE
└── README.md
✨ Key Features
🏥 Hospital Management
Patient registration and management
Hospital and facility management
Staff and role management
Appointment and scheduling
Ward, bed and inpatient management
Clinical records and documentation
💊 Pharmacy Management
Medication management
Electronic prescriptions
Dispensing
Pharmacy inventory
Stock and expiry tracking
Pharmacy administration
📹 Telemedicine
Doctor-patient video consultation
Real-time messaging
Remote healthcare access
LiveKit video infrastructure
Remote patient services
🚑 Emergency Healthcare
Emergency management
Patient triage
ICU management
Ambulance coordination
Emergency response workflows
🤖 AI-Powered Healthcare
AI-assisted triage
Diagnosis support
Clinical decision support
Risk prediction
Clinical text/NLP processing
Population health analytics
📱 Rural & Low-Connectivity Access
USSD healthcare services
Voice/IVR support
Community-based healthcare access
Local-language and accessibility support
🔗 Healthcare Interoperability
FHIR R4 support
EMR interoperability
Healthcare data exchange
Integration with external healthcare systems
🚀 Getting Started
Prerequisites

Install the following before running Tenadam:

Go 1.22+
Node.js 20+
Docker Desktop
Docker Compose
Git
PostgreSQL (optional when using Docker)
kubectl (only required for Kubernetes deployment)
⚙️ Installation
1. Clone the Repository
git clone https://github.com/Firaolfro/Tenadam-Digital-Health-Platform.git
cd Tenadam-Digital-Health-Platform
2. Configure Environment Variables

Copy the example environment file:

copy .env.example .env

On Linux/macOS:

cp .env.example .env

Update .env with your local configuration.

Never commit .env or other files containing passwords, API keys, tokens, or secrets.

🐳 Run with Docker

Start the development infrastructure:

docker compose up -d

Check running containers:

docker compose ps

Stop the system:

docker compose down
🗄️ Database

Run database migrations using the project's migration tooling:

make migrate

If you need to inspect the database containers:

docker compose ps

PostgreSQL, Redis and other infrastructure services can be managed through Docker Compose.

🌐 Start the Web Application

Go to the web application:

cd apps/web

Install dependencies:

npm install

Start development mode:

npm run dev

Then open:

http://localhost:3000
🔧 Run Backend Services

Example:

cd services/core/auth-service
go run ./cmd/main.go

Individual microservices can be started independently depending on the development requirement.

🛠 Useful Commands
Build
make build-all
Test Go Services
make test-go
Test Web Application
make test-web
Start Full System

Windows:

start-full-system.bat

or:

start-system.bat
📹 Telemedicine / LiveKit

Tenadam uses LiveKit for real-time video consultations.

Configure the following values in .env:

LIVEKIT_API_KEY=<your_api_key>
LIVEKIT_API_SECRET=<your_api_secret>
LIVEKIT_PUBLIC_URL=wss://<your-project>.livekit.cloud

Restart the API gateway after changing the configuration:

docker compose up -d api-gateway

For remote telemedicine testing, both clients should connect through the configured LiveKit Cloud server.

🔐 Security

Tenadam follows security-focused development practices including:

JWT authentication
Role-based access control
Multi-tenant data isolation
Audit logging
Secure environment configuration
Encrypted communication
API gateway security
Healthcare data protection

Never commit:

.env
.env.local
.env.production
API keys
JWT secrets
Database passwords
Private certificates
Production credentials
🏢 Multi-Tenancy

Tenadam is designed as a multi-tenant healthcare platform.

Healthcare organizations and resources are scoped using tenant information, allowing multiple healthcare institutions to operate securely within the same platform.

Authentication and authorization are handled through the core authentication services and API gateway.

🤖 AI Services

AI functionality is implemented using Python and FastAPI.

Planned/implemented AI capabilities include:

AI Triage
Diagnosis Support
Clinical Decision Support
Risk Prediction
NLP and Clinical Text Processing
Population Health Analytics
AI Audit Analysis
Healthcare Policy Compliance
📱 Mobile Application

The mobile application uses Capacitor to provide a native mobile experience from the web application codebase.

The architecture supports future Android and iOS deployment.

📞 USSD & Voice Services

Tenadam is designed to support users with limited internet connectivity through:

USSD healthcare services
Voice/IVR services
Community healthcare access
Rural healthcare support

This helps extend digital healthcare services beyond smartphone and high-speed internet users.

🧩 Microservice Structure

Each Go microservice follows a consistent structure:

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

This structure separates API handling, business logic, database access, domain models, and infrastructure concerns.

🔗 FHIR Integration

Tenadam supports healthcare interoperability through FHIR R4.

FHIR integration enables standardized exchange of healthcare information such as:

Patients
Practitioners
Organizations
Encounters
Observations
Medications
Medication Requests
Procedures
Diagnostic results
📚 Documentation

Additional project documentation is available in:

docs/

and the project root, including architecture, database, deployment, testing, pharmacy, staff management, and implementation guides.

🧪 Development

For development:

Clone the repository.
Configure .env.
Start Docker infrastructure.
Run database migrations.
Install frontend dependencies.
Start the required frontend and backend services.
Test the required modules.

Always create a separate Git branch when developing new features:

git checkout -b feature/your-feature-name
🤝 Contributing

Contributions should follow these guidelines:

Create a feature branch.
Follow the existing project structure.
Write or update tests.
Keep documentation updated.
Do not commit secrets or environment files.
Verify the application before creating a pull request.
📄 License

This project is licensed under the MIT License.

See:

LICENSE

for more information.

👨‍💻 Project

Tenadam Digital Healthcare System

An integrated digital health platform focused on improving healthcare accessibility, interoperability, and service delivery through modern software technologies.

Repository:
https://github.com/Firaolfro/Tenadam-Digital-Health-Platform
