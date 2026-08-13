# Tenadam Digital Healthcare System

**Tenadam** is an integrated digital healthcare platform designed to connect patients, healthcare professionals, hospitals, pharmacies, laboratories, emergency services, and community health agents through a unified digital ecosystem.

The platform combines **hospital management, telemedicine, pharmacy management, emergency response, clinical services, AI-powered healthcare support, USSD accessibility, interoperability, analytics, and public-health services** into a modular and scalable system.

Tenadam is designed with the Ethiopian healthcare context in mind, with particular attention to **urban–rural healthcare accessibility, low-connectivity environments, interoperability, multi-tenant healthcare organizations, and scalable digital health infrastructure**.

---

## 🌍 Vision

To provide an accessible, secure, intelligent, and interoperable digital healthcare ecosystem that improves healthcare delivery for both urban and rural communities.

## 🎯 Mission

Tenadam aims to:

- Improve access to healthcare services
- Connect patients with healthcare professionals
- Support hospitals and healthcare organizations with digital workflows
- Enable remote healthcare through telemedicine
- Improve pharmacy and medication management
- Support emergency healthcare services
- Provide AI-assisted healthcare decision support
- Enable healthcare access through USSD and low-connectivity channels
- Improve interoperability between healthcare systems
- Support data-driven healthcare management and public health surveillance

---

# 🏗 System Architecture

Tenadam follows a **modular, multi-tenant microservices architecture** organized as a monorepo.

| Layer | Technology |
|---|---|
| Backend Microservices | Go (Golang) |
| AI Services | Python + FastAPI |
| Web Frontend | Next.js 14 + App Router |
| Programming Language | TypeScript / Go / Python |
| Mobile | Capacitor |
| Database | PostgreSQL |
| Cache | Redis |
| Message Broker | Apache Kafka |
| Real-Time Communication | WebRTC / LiveKit |
| API Gateway | Go |
| Interoperability | FHIR R4 / HL7 |
| Containerization | Docker |
| Orchestration | Kubernetes |
| Infrastructure | Terraform |
| Testing | Go Testing / Jest / Playwright |
| Version Control | Git + GitHub |

---

# 📁 Repository Structure

```text
tenadam/
│
├── apps/
│   ├── web/
│   │   ├── patient-portal/
│   │   ├── org-portal/
│   │   ├── admin-portal/
│   │   └── ...
│   │
│   ├── mobile/
│   │   └── # Capacitor mobile application
│   │
│   └── ussd/
│       └── # USSD application
│
├── gateway/
│   └── api-gateway/
│       └── # Central API Gateway
│
├── services/
│   │
│   ├── core/
│   │   ├── auth/
│   │   ├── user/
│   │   ├── access-control/
│   │   ├── session/
│   │   ├── audit/
│   │   ├── consent/
│   │   └── config/
│   │
│   ├── registry/
│   │   ├── patient/
│   │   ├── practitioner/
│   │   ├── facility/
│   │   ├── organization/
│   │   ├── household/
│   │   └── identifier/
│   │
│   ├── clinical/
│   │   ├── encounter/
│   │   ├── clinical-data/
│   │   ├── procedure/
│   │   ├── careplan/
│   │   ├── note/
│   │   └── document/
│   │
│   ├── clinical-extensions/
│   │   ├── form/
│   │   ├── order/
│   │   ├── guideline/
│   │   ├── program/
│   │   └── terminology/
│   │
│   ├── diagnostics/
│   │   ├── lab/
│   │   ├── specimen/
│   │   ├── result/
│   │   ├── imaging/
│   │   └── radiology/
│   │
│   ├── pharmacy/
│   │   ├── medication/
│   │   ├── prescription/
│   │   ├── dispensing/
│   │   └── inventory/
│   │
│   ├── hospital/
│   │   ├── inpatient/
│   │   ├── ward/
│   │   ├── bed/
│   │   ├── nursing/
│   │   └── shift-handoff/
│   │
│   ├── emergency/
│   │   ├── emergency/
│   │   ├── triage/
│   │   ├── icu/
│   │   └── ambulance/
│   │
│   ├── surgery/
│   │   ├── surgery/
│   │   ├── theatre/
│   │   └── post-operative/
│   │
│   ├── operations/
│   │   ├── appointment/
│   │   ├── scheduling/
│   │   ├── queue/
│   │   └── referral/
│   │
│   ├── financial/
│   │   ├── billing/
│   │   ├── invoicing/
│   │   ├── claims/
│   │   ├── payment/
│   │   └── insurance/
│   │
│   ├── supply-chain/
│   │   ├── inventory/
│   │   ├── procurement/
│   │   ├── vendor/
│   │   └── warehouse/
│   │
│   ├── ai/
│   │   ├── triage/
│   │   ├── diagnosis-support/
│   │   ├── clinical-decision-support/
│   │   ├── risk-prediction/
│   │   ├── nlp/
│   │   ├── population-health/
│   │   ├── audit/
│   │   └── policy/
│   │
│   ├── telemedicine/
│   │   ├── video/
│   │   ├── chat/
│   │   └── remote-monitoring/
│   │
│   ├── communication/
│   │   ├── notification/
│   │   ├── messaging/
│   │   ├── ussd/
│   │   └── voice-tts/
│   │
│   ├── integration/
│   │   ├── fhir/
│   │   ├── interoperability/
│   │   └── event-bus/
│   │
│   ├── analytics/
│   │   ├── reporting/
│   │   ├── dashboards/
│   │   └── data-quality/
│   │
│   └── public-health/
│       ├── surveillance/
│       ├── outbreak-detection/
│       └── national-reporting/
│
├── backend/
│   └── # Backend components and supporting services
│
├── frontend/
│   └── # Frontend components and applications
│
├── packages/
│   ├── types/
│   ├── utils/
│   ├── logger/
│   ├── config/
│   ├── auth-client/
│   ├── db/
│   └── events/
│
├── database/
│   ├── migrations/
│   ├── seeds/
│   └── schemas/
│
├── infrastructure/
│   ├── docker/
│   ├── k8s/
│   ├── terraform/
│   └── scripts/
│
├── docs/
│   └── # Project documentation
│
├── tools/
│   ├── cli/
│   ├── codegen/
│   ├── admin-dashboard/
│   ├── backend-endpoint-tester/
│   └── backend-scan/
│
├── docker-compose.yml
├── Makefile
├── .env.example
├── .gitignore
├── LICENSE
└── README.md
