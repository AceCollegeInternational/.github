# Ace College International — Technology Division

> **"Every system we build is immediately accountable to real students,
> real parents, and real institutional consequences.
> We have never had the luxury of building in a sandbox."**

Lagos, Nigeria · Est. 2002 · [acecollege.com.ng](https://acecollege.com.ng)

---

## What This Organisation Is

ACE College International is a private secondary school in Ikorodu,
Lagos, Nigeria, serving 260+ students and 30+ staff.

This GitHub organisation is the open-source home of the school's
entire technology infrastructure — built and maintained by the
school's Proprietor & Lead Developer without external IT vendors,
without a CS degree, and without a staging environment that stays
staging forever.

Every repository here runs in production. Every commit has
real institutional consequences.

---

## The Infrastructure

| System | What It Does | Stack | Status |
|---|---|---|---|
| [sabi-api](https://github.com/AceCollegeInternational/sabi-api) | School intelligence API — at-risk detection, parent notifications, staff accountability | FastAPI · Python · MySQL · Telegram | 🟢 LIVE |
| [bursar-bot](https://github.com/AceCollegeInternational/bursar-bot) | WhatsApp fee query automation for 300+ students | n8n · WhatsApp Business API · MySQL | 🟢 LIVE |
| [fxguru-smc-ea](https://github.com/AceCollegeInternational/fxguru-smc-ea) | MQL5 Expert Advisor with four-state machine architecture | MQL5 · MetaTrader 5 · REST API | 🟢 LIVE |
| [ai-signal-bot](https://github.com/AceCollegeInternational/ai-signal-bot) | Python AI signal engine — SMC confluence scoring + LLM analysis | FastAPI · Python · Groq · Anthropic · Gemini | 🟢 LIVE |
| [ace-touch-typer](https://github.com/AceCollegeInternational/ace-touch-typer) | 143-lesson gamified typing curriculum on local Docker stack | HTML · JS · Docker · Nginx | 🔵 LOCAL |
| [essaymaster-pro](https://github.com/AceCollegeInternational/essaymaster-pro) | Gemini 2.0 Flash AI writing tutor for JSS3 students | HTML · JS · Gemini 2.0 Flash | 🟢 LIVE |
| [ace-server-stack](https://github.com/AceCollegeInternational/ace-server-stack) | Full school intranet — JupyterHub + OnlyOffice on a ₦180k laptop | Docker Compose · Nginx · MikroTik | 🔵 LOCAL |
| [ngx-research-bot](https://github.com/AceCollegeInternational/ngx-research-bot) | Multi-agent LLM equity research pipeline for Nigerian Exchange | n8n · LLM APIs · Google Sheets | 🟢 LIVE |
| [ace-gamified-lessons](https://github.com/AceCollegeInternational/ace-gamified-lessons) | 7+ standalone AI-integrated gamified lesson applications | HTML · JS · Web Audio · Gemini | 🟢 LIVE |

---

## The Architecture Philosophy

### Production-First
There is no test environment that never ships. Every system in
this organisation was built under the constraint that it would
serve real students, real parents, and real staff from day one.
That constraint produces different — and more considered —
architecture decisions than most development contexts allow.

### Institutional Resilience by Design
Systems are built so they survive beyond their original developer.
n8n over custom webhook handlers. Configuration files over
hardcoded values. Admin panels that allow non-technical staff
to operate systems without touching code. Documentation written
for the person who inherits this infrastructure, not the person
who built it.

### Zero-Vendor-Budget Innovation
The entire stack — from the school intranet running on a
repurposed laptop to the AI tutoring tools deployed in
classrooms — was built with open-source software and
free-tier cloud services. Commercial equivalents of these
systems would cost ₦2,000,000+ per year in licensing alone.

### Federation Over Migration
Where multiple databases exist, we federate rather than
migrate. The Sabi API reads across three live MySQL schemas
at query time — preserving 13 years of institutional data
integrity while enabling cross-system intelligence through
a single API layer.

---

## The Technical Environment
Languages       Python 3.11 · MQL5 · JavaScript (ES6+) · HTML5 · CSS3
Frameworks      FastAPI · n8n · Node.js
Databases       MySQL 8.0 · Three-schema federation
Infrastructure  Docker Compose · Ubuntu 24.04 · Caddy · Nginx · MikroTik
AI / LLM        Gemini 2.0 Flash · Anthropic Claude · Groq
Messaging       WhatsApp Business Cloud API · Telegram Bot API · OpenClaw
Trading         MetaTrader 5 · Exness Broker · SMC confluence engine
Hosting         Contabo VPS · Render · Hugging Face . Local HP Envy x360 (school server)

---

## Key Design Decisions

**Why three separate databases instead of one unified schema?**
The school ERP (`one_arps_aci`) was built by an external vendor
over 13 years. The Moodle LMS (`studypal`) uses its own data
model. Migrating either would risk catastrophic data loss with
no recovery path. The Sabi API federates across all three at
runtime — treating the integration layer as the engineering
problem, not the data itself.

**Why n8n for the Bursar Bot instead of custom Python?**
A custom FastAPI webhook handler would require a developer
to modify code every time a message template changes. n8n
allows non-technical administrators — a bursar, a school
secretary — to adjust notification schedules and message
content without touching the codebase. The system is designed
to outlast direct developer involvement.

**Why single-file HTML for classroom tools?**
Classroom devices in Lagos operate with unreliable internet.
A single-file application with no external CDN dependencies
functions from a USB drive, a local file server, or a direct
email attachment. Every lesson in the gamified suite works
offline. Every tool that requires AI routes gracefully when
the API is unavailable.

---

## Community

**studypalNG** — YouTube channel for Nigerian students and educators.
Currently home to study-focused short-form content. Expanding in 2026
to document the school operations automation, AI classroom tools, and
EdTech infrastructure builds featured in this organisation — making
the technical journey visible to Nigerian school owners and developers
who face the same problems.

▶ [youtube.com/@studypalNG](https://youtube.com/@studypalNG)

---

## The Broader Goal

Nigeria has 35,000+ private secondary schools.
Fewer than 3% have any form of automated operations.

The tools in this organisation were built for ACE College
International. They are open-sourced here so that any school
proprietor, developer, or EdTech builder who faces the same
problems can deploy, fork, and adapt them without starting
from scratch.

The unit economics of building for Nigerian secondary schools
look small in Lagos. They look significant everywhere else.

---

## Built By

**Principal & Lead Developer**
ACE College International · Ikorodu, Lagos, Nigeria
Self-taught trajectory: PHP scripting (2019) → multi-system
production architecture (2021). No CS degree.
Every system deployed into a live institution with real
accountability from day one.

→ [LinkedIn](https://www.linkedin.com/in/kalu-olugu)

---

*All repositories are open-source unless otherwise stated.*
*Production credentials, student data, and broker configurations*
*are excluded from all public releases.*
*See individual repository SECURITY.md files for responsible*
*disclosure guidelines.*
