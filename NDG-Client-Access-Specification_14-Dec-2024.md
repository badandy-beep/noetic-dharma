# NDG Client Access Portal — Feature Specification
## Created: 14-Dec-2024
## Status: PLANNED (Placeholder Deployed)

---

## OVERVIEW

The Client Access Portal provides secure, PIN-authenticated access for NDG clients to view draft materials, strategic documents, pitch decks, and other confidential assets prepared specifically for them.

---

## USER FLOW

### Step 1: PIN Entry
- Client clicks "Client Access" in nav or footer
- Arrives at `client-access.html`
- Visual: Socrates (contemplating) on LEFT, PIN entry box on RIGHT
- Client enters 6-digit PIN provided by their NDG principal

### Step 2: Registration Modal (First-Time Access)
After valid PIN, popup modal appears:
```
┌─────────────────────────────────────┐
│     VERIFY YOUR IDENTITY            │
│                                     │
│  First Name: [____________]  *      │
│  Last Name:  [____________]  *      │
│  Email:      [____________]  *      │
│  Phone:      [____________]  *      │
│                                     │
│  [    SEND VERIFICATION CODE    ]   │
│                                     │
│  Your phone number will receive     │
│  a one-time verification code.      │
└─────────────────────────────────────┘
```

### Step 3: SMS Verification
- System sends 6-digit code via SMS (Twilio)
- Client enters code in verification modal
- Code expires in 10 minutes
- 3 attempts max before lockout

### Step 4: Access Granted
- Client sees their project materials:
  - PDFs
  - Pitch decks (PPTX/PDF)
  - Draft documents
  - Custom applications
  - Video content (if applicable)
- All files include disclaimer overlays
- Download tracking enabled

---

## TECHNICAL ARCHITECTURE

### Frontend (client-access.html)
```
Current: Static placeholder with PIN input
Future:  React component with modal system
```

### Backend Requirements
| Component | Recommended Service | Purpose |
|-----------|-------------------|---------|
| PIN Storage | Supabase / Firebase | Encrypted PIN database |
| SMS Verification | Twilio Verify | Send/validate codes |
| File Storage | Supabase Storage / S3 | Secure file hosting |
| User Sessions | Supabase Auth | Track authenticated users |
| Access Logging | Supabase / Custom | Audit trail |

### Database Schema (Planned)

**Table: projects**
```sql
id              UUID PRIMARY KEY
pin             VARCHAR(6) UNIQUE -- hashed
project_name    VARCHAR(255)
client_name     VARCHAR(255)
client_company  VARCHAR(255)
created_at      TIMESTAMP
expires_at      TIMESTAMP
is_active       BOOLEAN DEFAULT true
```

**Table: project_files**
```sql
id              UUID PRIMARY KEY
project_id      UUID REFERENCES projects(id)
file_name       VARCHAR(255)
file_url        TEXT
file_type       VARCHAR(50) -- pdf, pptx, app, video
display_order   INTEGER
disclaimer_text TEXT
created_at      TIMESTAMP
```

**Table: access_logs**
```sql
id              UUID PRIMARY KEY
project_id      UUID REFERENCES projects(id)
user_phone      VARCHAR(20)
user_email      VARCHAR(255)
user_name       VARCHAR(255)
accessed_at     TIMESTAMP
ip_address      VARCHAR(45)
user_agent      TEXT
files_viewed    JSONB
```

**Table: verification_codes**
```sql
id              UUID PRIMARY KEY
phone           VARCHAR(20)
code            VARCHAR(6) -- hashed
created_at      TIMESTAMP
expires_at      TIMESTAMP
attempts        INTEGER DEFAULT 0
verified        BOOLEAN DEFAULT false
```

---

## SECURITY REQUIREMENTS

### PIN Security
- [ ] 6-digit numeric PINs
- [ ] Hashed storage (bcrypt)
- [ ] Rate limiting: 5 attempts per IP per hour
- [ ] PINs expire after configurable period (default 90 days)
- [ ] One PIN per project

### SMS Verification
- [ ] Twilio Verify API
- [ ] 6-digit codes, 10-minute expiry
- [ ] 3 attempts max per session
- [ ] Phone number validation (E.164 format)
- [ ] US phone numbers only (initially)

### Session Management
- [ ] JWT tokens with 24-hour expiry
- [ ] Secure, httpOnly cookies
- [ ] Session invalidation on browser close
- [ ] Re-verification required after 7 days

### File Security
- [ ] Signed URLs with 1-hour expiry
- [ ] No direct file links
- [ ] Watermarking on PDFs (client name + timestamp)
- [ ] Download logging

---

## DISCLAIMER REQUIREMENTS

All materials must display:

```
CONFIDENTIAL & PROPRIETARY
© 2025 Noetic Dharma Group, LLC

This document is prepared exclusively for [CLIENT_NAME] and contains 
confidential information. Unauthorized distribution is prohibited.

DRAFT — For Discussion Purposes Only
This material is preliminary and subject to revision.

Prepared: [DATE]
Project: [PROJECT_NAME]
```

---

## ADMIN INTERFACE (Future Phase)

NDG principals will need ability to:
- Create new project PINs
- Upload files to projects
- Set expiration dates
- View access logs
- Revoke access
- Download audit reports

**Recommended**: Build admin in Supabase Studio initially, then custom React dashboard later.

---

## IMPLEMENTATION PHASES

### Phase 1: Placeholder (CURRENT)
- [x] Static client-access.html page
- [x] PIN input UI
- [x] Socrates visual + quote
- [x] Link in nav and footer
- [ ] Alert explaining "coming soon"

### Phase 2: Basic Authentication
- [ ] Supabase project setup
- [ ] PIN validation endpoint
- [ ] Registration modal
- [ ] Twilio SMS integration
- [ ] Basic file display

### Phase 3: File Management
- [ ] Secure file upload
- [ ] PDF watermarking
- [ ] Download tracking
- [ ] Expiration handling

### Phase 4: Admin Dashboard
- [ ] Project creation UI
- [ ] File management UI
- [ ] Access logs viewer
- [ ] Bulk operations

---

## THIRD-PARTY SERVICES REQUIRED

| Service | Purpose | Est. Cost |
|---------|---------|-----------|
| Supabase | Database, Auth, Storage | Free tier / $25/mo |
| Twilio Verify | SMS codes | ~$0.05/verification |
| Vercel | Hosting | Free tier |

---

## INTEGRATION WITH NDG WORKFLOW

1. NDG principal prepares materials for client
2. Principal creates project in admin, uploads files
3. System generates unique 6-digit PIN
4. Principal shares PIN with client (email/call)
5. Client accesses materials via portal
6. System logs all access for compliance
7. Materials auto-expire after project completion

---

## NOTES FOR CLAUDE

When building this feature:
- Use Supabase for all backend (simplest stack)
- Twilio Verify for SMS (most reliable)
- Keep frontend in vanilla JS initially (avoid React complexity)
- Prioritize security over features
- All file URLs must be signed/expiring
- Log everything for audit purposes

---

© 2025 Noetic Dharma Group, LLC | CONFIDENTIAL & PROPRIETARY
