# 💸 MoneyLend — Digital Mutual Agreement & Trust-Based Lending Platform

> A smart money lending platform that turns informal loans into digitally signed agreements with a reputation-based trust system — built for HackMol 7.0

---

## 👥 Team Details

| Field | Details |
|---|---|
| **Team Name** | Tech Freakers |
| **Members** | [Member 1 Name] · [Member 2 Name] · [Member 3 Name] · [Member 4 Name] |
| **College** | [College Name] |
| **City, State** | [City], [State] |

---

## 🚨 Problem Statement

Informal money lending between friends, family, and small business owners is extremely common in India — yet it is almost entirely undocumented. This leads to:

- **No proof of agreement** — disputes arise with no evidence on either side
- **No accountability** — borrowers delay or ignore repayments with no consequence
- **No trust system** — lenders have no way to assess if someone is a reliable borrower
- **No structured reminders** — lenders awkwardly have to personally follow up
- **Strained relationships** — money disputes damage personal and professional bonds
- **No partial repayment structure** — lenders can't formally offer instalment options

Existing banking and fintech solutions (banks, NBFCs, apps like KhataBook) either require heavy documentation/KYC, don't support peer-to-peer agreements, or lack any behavioural trust tracking.

**Millions of small business owners and individuals have no safe, lightweight, and legally-structured way to lend money to people they know.**

---

## 💡 Proposed Solution

**MoneyLend** is a cross-platform (Android + Web) money lending management app that introduces the concept of a **Digital Mutual Agreement (DMA)** — a digitally signed, consent-based lending contract between two parties, paired with a **Reputation Badge System** that tracks repayment behaviour over time.

### How it's better than existing solutions

| Feature | KhataBook / Vyapar | Banks / NBFCs | MoneyLend |
|---|---|---|---|
| Peer-to-peer agreements | ❌ | ❌ | ✅ |
| Digital e-sign by both parties | ❌ | ❌ | ✅ |
| Reputation/Trust tracking | ❌ | Partial (CIBIL) | ✅ |
| SMS-based agreement flow | ❌ | ❌ | ✅ |
| Partial repayment flexibility | ❌ | ✅ | ✅ |
| Works without app install | ❌ | ❌ | ✅ (Web fallback) |
| UPI payment integration | ❌ | ✅ | ✅ |
| Free tier available | ✅ | ❌ | ✅ |

---

## 🪜 How It Works — Step by Step

### For the Lender (Person B)
1. Opens **MoneyLend** Android app and taps **"Create Agreement"**
2. Enters borrower's name, mobile number, loan amount, deadline date, and repayment mode (lump sum or instalments)
3. Taps **Send Request** → system generates a unique agreement and sends an SMS to the borrower via **Fast2SMS**

### For the Borrower (Person A) — App Installed
4. Receives SMS with a secure agreement link
5. Link opens the MoneyLend app via deep link → user info is auto-fetched
6. Borrower reviews the full terms & conditions → taps **Accept & Sign**
7. Agreement is digitally locked — both parties receive confirmation

### For the Borrower (Person A) — No App Installed
4. Receives SMS → clicks link → mobile web page opens
5. Sees: *"Download MoneyLend for better experience"* + premium feature highlights
6. Can either download the app OR fill in basic details to sign directly on the web
7. Agreement is completed and locked

### Repayment Flow
8. As the deadline approaches, smart reminders are sent via SMS (timing adjusted per borrower's repayment history)
9. Borrower clicks reminder link → lands on payment page → pays via **UPI**
10. Both lender and borrower confirm the transaction → **Reputation Badge updates** for the borrower

### Missed Payment Flow
11. If deadline is missed → borrower receives a **poll SMS** asking why
12. Based on response + reputation badge status → penalty applied, instalment option offered, or new deadline assigned
13. Persistent defaults → auto-debit warning issued *(simulated in MVP; requires RBI integration in production)*

---

## ✨ Features

### 🤝 Digital Mutual Agreement (DMA)
- Lender (Person B) enters borrower's name, mobile number, loan amount, repayment deadline, and repayment mode (lump sum or instalments)
- System sends an **SMS via Fast2SMS** to the borrower with a secure agreement link
- If borrower has the app installed → app opens automatically, pre-fills user info, and presents the full agreement with terms & conditions to accept
- If borrower does NOT have the app → a mobile-optimised **web page** opens showing:
  - Option to download the app (with highlighted premium features to nudge download)
  - Option to complete agreement directly on the web by entering basic details
- Both parties digitally sign → agreement is locked

### 🏅 Reputation Badge System (replaces "Trust Factor")
- Tracks every repayment event: on-time, late, or missed
- Badge tiers (e.g., Bronze → Silver → Gold → Platinum) based on repayment history
- Social proofs displayed on profile: *"This person has repaid 12 loans successfully"*
- Badges are visible to lenders before approving any new loan request
- **Trust score updates only when both parties confirm** — lender confirms money sent, borrower confirms money received

### 📊 Lender Dashboard
- Overview of: total money lent, money recovered, pending repayments, at-risk borrowers
- Recovery rates and risk user flags
- Caller button: if a borrower is significantly overdue, a **one-tap call shortcut** appears on the dashboard with the borrower's name (opens native Android dialer)

### 🔔 Smart Adaptive Reminders
- Reminder timing is personalised based on repayment behaviour:
  - Borrowers with a history of delays → reminders sent early
  - Reliable borrowers → reminders sent close to the due date
- Reminder SMS links to the payment page directly

### 📋 Repayment Poll (Missed Payment Flow)
When a borrower misses a deadline, they receive an SMS with a link that takes them to a poll:
- Why did you miss the payment?
  - 💸 No money right now
  - 😅 I forgot
  - 🔄 Other
  - (Ignored / no response)
- If "No money" is selected AND the lender has enabled the instalment option AND borrower has a good reputation badge:
  - Penalty is applied (reputation impact)
  - Option to repay in instalments is offered
  - A new due date is assigned
- If the new due date is also missed:
  - Second warning issued
  - Further badge degradation
  - If badge is below threshold: auto-debit warning message is shown (simulated in MVP; requires RBI integration in production)

### 💳 UPI Payment Integration (Web App)
- Borrowers can repay directly through the web app via UPI
- Smart chain repayment notification: if A lent to B and B received repayment, A is notified — *"You received ₹X from B. You also owe ₹Y to C."*

### 📤 Loan Request Feature
- Users can browse public lender profiles or send loan requests via mobile number
- **Daily request limit** per user to prevent spam

### 🌐 Freemium Model
- Web app is free with ads
- Premium plan available (removes ads, adds advanced analytics, more storage)
- Premium revenue covers: database hosting, SMS API costs, server costs

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Android App | Kotlin |
| Web App | Next.js (React) |
| Backend/API | Node.js / Next.js API Routes |
| Database | [e.g., Firebase / PostgreSQL / Supabase] |
| SMS Service | Fast2SMS API |
| Payments | UPI Deep Link / Razorpay (Web) |
| Authentication | [e.g., Firebase Auth / OTP-based] |
| Hosting | [e.g., Vercel / Railway / AWS] |

---

## 🔄 Workflow Diagram

```
LENDER (Person B)
      │
      ▼
Enter: Borrower name, mobile, amount, deadline, repayment mode
      │
      ▼
System sends SMS (Fast2SMS) ──────────────────────────────────────┐
      │                                                            │
      ▼                                                            ▼
BORROWER (Person A)                                    BORROWER (Person A)
  [App Installed]                                       [No App]
      │                                                            │
App opens via deep link                              Web page opens
Pre-fills user info                                  (Download CTA + Web sign option)
      │                                                            │
      └──────────────────────┬─────────────────────────────────────┘
                             │
                             ▼
              Reviews Terms & Conditions
                             │
                             ▼
                  Digitally Signs Agreement (DMA)
                             │
                  ┌──────────┴──────────┐
                  ▼                     ▼
           Repayment Due           Missed Payment
                  │                     │
           UPI Payment             Poll Sent via SMS
           Confirmation            (No Money / Forgot / Other)
                  │                     │
           Both confirm         Reputation Badge Updated
                  │             Penalty / Instalment Option
           Badge Updated              │
                                 New Due Date Assigned
                                       │
                                 (If missed again → Warning → Auto-debit simulation)
```

---

## 🎯 Target Audience & Engagement

### Primary Users
- **Small business owners & shopkeepers** who regularly give credit/loans to known people
- **Individual lenders** — friends or family who lend money informally

### Secondary Users
- **Borrowers** who receive loans and need a structured repayment interface

### Engagement Strategy
- Reputation badges create a **social incentive** to repay on time
- Public lender profiles and social proofs drive organic trust-building
- Freemium model lowers the barrier to entry; premium features create upgrade motivation
- Adaptive reminders reduce friction and increase on-time repayment rates
- SMS-based flow ensures even users without the app are captured in the ecosystem

---

## 🔮 Future Scope

1. **KYC Integration** — Aadhaar/PAN-based identity verification for higher loan limits
2. **Bank Integration & Auto-Debit** — RBI-compliant mandate system for automatic deductions on default (currently simulated in MVP)
3. **Legal Partnerships** — Tie-ups with legal firms to make DMAs court-admissible
4. **Credit Score Integration** — Link reputation badges with formal credit bureaus (CIBIL, Experian)
5. **Third-Party Escrow/Bank as Witness** — A neutral financial institution holds the agreement as a guarantor, adding legal pressure
6. **Group Lending / Chit Fund Support** — Multi-party lending agreements
7. **AI-Based Risk Assessment** — Predict default probability based on repayment history trends

---

## ⚠️ Risks & Mitigation

| Risk | Mitigation |
|---|---|
| Data misuse / privacy breach | End-to-end encryption, minimal data collection, clear privacy policy |
| Fake agreements | OTP-based identity confirmation at time of signing |
| No legal enforceability (currently) | Positioned as social/moral accountability tool; legal enforceability in future scope via KYC + legal partnerships |
| System trust abuse | Reputation badge only updates with dual confirmation (both parties must confirm) |
| SMS spam via request feature | Daily request limit per user |

---

## 💰 Economic Viability

- **Free tier**: Supports basic lending with ads → zero barrier to entry
- **Premium tier**: ₹[X]/month → removes ads, advanced analytics, higher SMS quota
- **Revenue sources**: Ad revenue (free users) + Premium subscriptions
- **Cost coverage**: SMS API (Fast2SMS), cloud hosting, database storage
- **Scalable**: As user base grows, ad revenue scales; premium conversion expected from business users who need advanced dashboard features

---

> *Built with ❤️ by Team Tech Freakers for HackMol 7.0 — NIT Jalandhar*
