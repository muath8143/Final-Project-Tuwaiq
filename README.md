# Abdulmajed’s Contributions

---

##  Roles
- **Owner / Contributor:** Abdulmajed
- **Area:** Backend (Security + Auth + Customer + CV + Integrations)
- **Access:** JWT-based authentication + roles/authorities integration

---

##  Workflow
1. **Authentication**
   - User logs in → receives **JWT token**
   - Token is used to access protected endpoints based on **roles/authorities**
2. **Customer Module**
   - Customer registers
   - Customer manages account (update/delete)
3. **CV Module**
   - Authenticated user can manage CV (CRUD + “My CV” retrieval)
4. **CV Upload Pipeline**
   - Upload CV PDF
   - Extract text from PDF (PDFBox)
   - Send extracted text to **n8n webhook** for parsing
   - Map parsed fields and save CV
5. **PDF Output**
   - Generate CV as PDF and download as attachment
6. **Email Delivery**
   - Send generated CV PDF to a recipient email
7. **AI Recommendations**
   - Retrieve CV improvement suggestions via **OpenAI** endpoint

---

##  Key Features (Implemented by Abdulmajed)
- Spring Security configuration (**JWT + roles/authorities integration**)
- JWT Filter + password encoding (**PasswordEncoder**)
- Authentication flow (**Login → JWT token**)
- Customer module endpoints (**register + account management**)
- CV module (**CRUD + “My CV” retrieval**)
- CV upload flow (**PDF upload → extract text → n8n parse → save CV**)
- CV PDF generation endpoint (**download as attachment**)
- CV email sending endpoint (**send generated CV PDF to recipient**)
- OpenAI CV recommendations endpoint (**cvImprovementSuggestions usage**)
- CV PDF HTML template using **Thymeleaf** (professional resume layout used in PDF generation)
- Overall backend architecture + initialized project scaffolding (packages/modules/folders)
- Shared conventions and base layers (DTO IN/OUT, Advice/exception handling structure, validation groups, Thymeleaf templates setup)

---

## Tech Stack (Relevant to my scope)
| Area | Technology |
|---|---|
| Backend | Spring Boot |
| Security | Spring Security + JWT |
| Password Hashing | PasswordEncoder |
| PDF Text Extraction | PDFBox |
| Workflow Integration | n8n Webhook |
| AI | OpenAI |
| PDF Generation | Thymeleaf HTML template → PDF |
| Email | [Fill: mail provider / library if you want to mention it] |

---

##  Configuration (What this module needs)
> Fill these with the real names/keys you used in `application.properties` or env.

- **JWT**
  - `JWT_SECRET` = [Fill]
  - `JWT_TTL_SECONDS` = [Fill]
- **n8n**
  - `N8N_WEBHOOK_URL` = [Fill]
- **OpenAI**
  - `OPENAI_API_KEY` = [Fill]
- **Email**
  - `MAIL_HOST` = [Fill]
  - `MAIL_PORT` = [Fill]
  - `MAIL_USERNAME` = [Fill]
  - `MAIL_PASSWORD` = [Fill]
  - `MAIL_FROM` = [Fill]

---

##  Project Structure (Related packages / modules)
- `config/` → security configuration, JWT setup, filters
- `controllers/` → Auth, Customer, CV endpoints
- `services/` → CV logic, PDF parsing, n8n integration, OpenAI integration, PDF generation
- `repositories/` → persistence layer for customer/CV
- `dtos/` → DTO IN/OUT + validation groups
- `advice/` → exception handling structure
- `resources/templates/` → `resume.html` (Thymeleaf)

---

##  Security Notes
- Stateless JWT authentication
- Role/authority-based access for protected endpoints
- Public endpoints: customer registration + login (as per design)
- CV operations are protected for authenticated users

---

# API Endpoints (Abdulmajed)

## Auth
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| POST | `/api/v1/auth/login` | Login and return JWT token | No |
| GET  | `/api/v1/auth/test/role` | Return current user authorities (debug) | Yes |

---

## Customer
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| POST | `/api/v1/customer/register-customer` | Register a new customer | No |
| GET  | `/api/v1/customer/get-customers` | Get all customers | (Project rules) |
| PUT  | `/api/v1/customer/update-customer` | Update authenticated customer | Yes |
| DELETE | `/api/v1/customer/delete-customer` | Delete authenticated customer | Yes |

---

## CV
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| GET | `/api/v1/cv/get-all-cv` | Get all CVs | (Project rules) |
| GET | `/api/v1/cv/get-my-cv` | Get CV for authenticated user | Yes |
| POST | `/api/v1/cv/create-cv` | Create CV for authenticated user | Yes |
| PUT | `/api/v1/cv/update-cv` | Update CV for authenticated user | Yes |
| DELETE | `/api/v1/cv/delete-cv` | Delete CV for authenticated user | Yes |

---

## CV Upload
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| POST | `/api/v1/cv/upload-cv` | Upload CV PDF, extract text, parse via n8n, then save CV | Yes |

---

## CV PDF
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| GET | `/api/v1/cv/download-generate-cv` | Generate and download CV as PDF (attachment) | Yes |

---

## CV Email
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| POST | `/api/v1/cv/send-cv-to-email` | Send generated CV PDF to a recipient email | Yes |

---

## AI (OpenAI)
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| GET | `/api/v1/cv/get-recommendation` | Get CV improvement suggestions from AI | Yes |

---

# Services (Abdulmajed)

| Service | Main Responsibility |
|---|---|
| `CVService` | CV CRUD, upload+parse flow, and AI recommendations orchestration |
| `PDFParserService` | Extract text from uploaded CV PDF using PDFBox |
| `N8nIntegrationService` | Send CV text to n8n webhook and map parsed CV fields |
| `OpenAiService` | Generate CV improvement suggestions (cvImprovementSuggestions endpoint) |
| `CvPdfGeneratorService` | Generate CV PDF using Thymeleaf HTML template (professional resume layout) |

---

# Templates (Abdulmajed)
- `resume.html` (Thymeleaf): Professional Resume HTML template used for CV PDF generation
