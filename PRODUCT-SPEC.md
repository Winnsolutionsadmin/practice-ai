# PracticeAI — Product & Technical Delivery Spec

## Product Summary
**Name:** PracticeAI
**Category:** AI Practice Management Automation
**Price:** $999/mo (Foundation) | $1,999/mo (Full Practice) | Custom (Multi-Site)
**Setup Fee:** $3,000 (Full Practice)
**Delivery Model:** Done-for-you managed service + software platform
**Contract:** Month-to-month (annual pre-pay: 2 months free)

---

## Core Systems

### System 1: Patient Flow Automation (Pre-Visit)

**1.1 Appointment Booking**
- 24/7 AI-powered booking via practice website widget, SMS keyword, and voice (IVR)
- Syncs with EHR/PMS scheduling calendar in real-time
- Respects provider templates, blocked times, and appointment types
- Sends immediate confirmation to patient (SMS + email)

**1.2 Multi-Channel Reminder Cascade**
- Reminder schedule (configurable): 7 days → 48 hours → 24 hours → 2 hours
- Channel cascade: SMS primary → email → voice call (if no SMS response)
- Two-way confirmation: patient replies CONFIRM/CANCEL/RESCHEDULE
- On cancellation: instant waitlist notification to next eligible patient
- On reschedule request: AI offers available slots, completes rebooking

**1.3 Insurance Pre-Verification**
- Triggers automatically 24–48 hours before appointment
- Checks: active coverage, plan type, copay/deductible, referral requirements, pre-authorization flags
- Flags discrepancies before patient arrives (staff review queue)
- Integrates with: Availity, Relay Health, Change Healthcare, payer portals
- Average completion time: 14 minutes per patient
- Error flagging: pre-auth missing, coverage inactive, plan mismatch

**1.4 Digital Intake**
- Custom intake forms per specialty (demographic, medical history, consent)
- Sent 48 hours before appointment via SMS/email link
- HIPAA-compliant form delivery (encrypted, no PHI in SMS)
- Completed data auto-imports to EHR on staff review approval
- Tracks completion rate; sends reminder if not completed in 24 hours

---

### System 2: Day-of Operations

**2.1 Pre-Loaded Patient Record**
- Completed intake forms available in EHR before patient walks in
- Insurance verification status flag visible to front desk
- Outstanding balance + copay expectation displayed

**2.2 Patient Communication**
- "Running late?" patient-initiated SMS to front desk (routed through AI, logged)
- Provider running behind: AI sends proactive update to waiting patients
- Post-visit instructions: delivered via SMS within 5 minutes of checkout

**2.3 Review Generation**
- Satisfaction prompt sent 2–4 hours after visit via SMS
- 4–5 star response: redirected to Google/Yelp review link
- 1–3 star response: routed to internal feedback (never public), office manager notified
- Monthly review report with trends and response rate

**2.4 Payment Collection**
- Balance reminder sent with payment link on checkout confirmation
- Automated payment plan offer for balances over $300
- Integration with practice billing (Kareo, AdvancedMD, AthenaHealth billing)

---

### System 3: Patient Retention (Post-Visit)

**3.1 Recall Campaign Engine**
- Recall interval detection from last visit type and specialty protocol
- Outreach sequence: SMS at 2 weeks before due → email at 1 week → voice call at due date
- Sequence stops on booking confirmation
- Recall analytics: outreach sent, opened, booked, no-response rate per cohort

**3.2 Chronic Disease Management Follow-Up**
- Configurable follow-up sequences for: diabetes, hypertension, asthma, mental health, dental care
- AI sends personalized check-in messages aligned with care protocols
- Escalation pathway: if patient flags concern, routes to clinical team

**3.3 Lapsed Patient Reactivation**
- Identifies patients with no visit in 12–24 months
- Automated "we miss you" sequence with re-engagement offer
- Segments by last visit type, age, insurance status

**3.4 Birthday + Milestone Campaigns**
- Birthday SMS/email sequence (configurable)
- Practice anniversary ("you've been with us 5 years") milestone message
- Holiday scheduling reminders (back to school, year-end benefits)

---

## Technical Architecture

### Integration Layer
- **EHR/PMS Supported:** Athenahealth, eClinicalWorks, Dentrix, Eaglesoft, Kareo, Office Ally, OpenDental, SimplePractice, Therapynotes, DrChrono, Modernizing Medicine, AdvancedMD
- **Integration method:** HL7 FHIR API (preferred) or bidirectional sFTP + webhook where FHIR unavailable
- **Custom integrations:** Available for systems not on standard list (add $500/mo)

### Infrastructure
- Cloud: AWS HIPAA-eligible architecture (us-west-2)
- SMS: Twilio HIPAA-compliant messaging (encrypted at rest)
- Email: SendGrid HIPAA-compliant tier
- Voice: Twilio Programmable Voice + ElevenLabs TTS for natural-sounding calls
- Database: PostgreSQL (encrypted) — no PHI in AI training datasets
- Monitoring: Datadog + PagerDuty for 99.9% uptime SLA (Multi-Site plan)

### Security & Compliance
- HIPAA Business Associate Agreement (BAA) — signed with all clients
- Data encryption: TLS 1.3 (transit), AES-256 (at rest)
- Access controls: Role-based, per-user audit logs
- PHI never leaves US-based AWS infrastructure
- Annual third-party security audit
- SOC 2 Type II (in progress, available Q3 2026)
- Penetration testing: semi-annual

---

## Implementation Process

### Week 1: Integration & Configuration
- Day 1: EHR credentials provided, technical setup begins
- Day 2–3: Integration testing (read/write appointment data, patient demographics)
- Day 4: Reminder templates configured to practice voice and protocols
- Day 5: Insurance verification configured for practice payer mix
- Day 5: Staff training session (2 hours, remote, recorded for future reference)

### Week 2: Go-Live
- Day 8: System goes live for new appointments only
- Day 8–14: Implementation manager monitors daily, flags any anomalies
- Day 10: First weekly performance report delivered to practice manager
- Day 14: Full go-live review call — adjust any configuration

### Ongoing
- Monthly performance report (no-show rate, verification stats, recall rate, ROI summary)
- Quarterly business review call with account manager
- 24/7 support via email + business hours phone support

---

## Service Delivery Team

| Role | Responsibility |
|------|----------------|
| Implementation Manager | Setup, integration, onboarding, weeks 1–2 |
| Account Manager | Ongoing relationship, monthly reviews, upsell |
| Technical Support | Integration issues, system config changes |
| AI Training Specialist | Custom language model tuning for practice voice |

**Staffing model:** 1 account manager per 15 clients (Full Practice tier)

---

## Deliverables per Client

**At Launch:**
- [ ] EHR integration live and tested
- [ ] Reminder sequences configured and approved
- [ ] Insurance verification workflow tested
- [ ] Digital intake forms built to spec
- [ ] Staff training completed
- [ ] BAA signed and filed
- [ ] Baseline metrics captured (no-show rate, current recall rate)

**Monthly:**
- [ ] Performance report (no-show rate, verification success rate, recall conversion)
- [ ] ROI summary vs. previous month and baseline
- [ ] Any sequence or template updates based on performance

---

## Metrics & SLAs

| Metric | SLA |
|--------|-----|
| System uptime | 99.5% (Full Practice) / 99.9% (Multi-Site) |
| Reminder delivery | <60 seconds from scheduled time |
| Insurance verification | <20 min per patient (business hours) |
| Integration setup | 7 business days from credentials received |
| Support response | <4 hrs (email), <2 hrs (phone, Multi-Site) |
| Monthly report delivery | By 5th of following month |

---

## 90-Day Performance Guarantee Terms
- Guaranteed minimum: 3x monthly fee recovered in documented value within 90 days
- Measurement: baseline no-show rate vs. 90-day no-show rate × appointment value + staff time saved (at market rate)
- If threshold not met: client receives credit for the shortfall against future months (or refund if cancelling)
- Exclusions: force majeure, practice-side delays in integration/onboarding >2 weeks

## Linked Files
See also: [[BRAND]], [[MARKETING]], [[OUTREACH]], [[ADS]]
