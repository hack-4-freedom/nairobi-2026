# BillBridge

**Transparent fundraising, borderless contributions.**

## Overview

BillBridge is a transparent cross-border fundraising platform that enables families, friends, and diaspora communities to contribute towards **verified institutional bills** such as school fees, hospital bills, and community projects in Kenya.

Donors can contribute using **Bitcoin Lightning**, while institutions receive funds in **Kenyan shillings through their verified official payment channels**. Donors do not need to understand Bitcoin; Lightning serves as the fast and low-cost payment rail behind the experience.

BillBridge places the institution at the centre of the transaction by verifying beneficiaries, directing contributions to official institutional payment channels, tracking payments, and providing donors with confirmation that their contribution reached the intended institution.

The project was built at **Hack4Freedom Nairobi 2026** following the H.A.U.T.E. framework:

* **H — Human first:** Preserves the spirit of harambee while making cross-border giving easier.
* **A — Accessible:** Web, USSD, multiple currencies, and an AI help chatbot.
* **U — Useful now:** Works with familiar institutional PayBill payment channels.
* **T — Trustworthy:** Verified institutions, official payment destinations, transaction tracking, and institutional receipts.
* **E — Easy:** Shareable campaign links, QR codes, and a guided donation process.


## Problem

Families in Kenya and the diaspora already contribute collectively towards school fees, medical bills, and community projects. However, cross-border fundraising presents two major challenges.

### Cost

International transfers and card-based payment methods can involve significant transaction costs, making smaller contributions less practical.

### Trust

Donors may send money through an individual's phone or personal account without being certain that:

* The person is genuinely collecting for the stated institution.
* The money will reach the intended institution.
* The stated bill actually exists.
* The institution has received the contribution.
* The contribution has been properly accounted for.

This creates a gap between **making a contribution** and **knowing that it reached the intended destination**.



## Solution

BillBridge creates a verified connection between **donors and institutions**.

### 1. Campaign creation

An organizer creates a campaign through the web platform or USSD and provides the institution's official PayBill and relevant bill information.

### 2. Institution verification

The institution and its payment details are checked against BillBridge's institution registry.

Personal wallets and unrecognized payment numbers are not accepted as institutional beneficiaries.

### 3. Donor contribution

Donors can contribute from anywhere through the donation interface.

The platform supports:

* Bitcoin Lightning
* Currency conversion
* QR-based payments
* Simulated mobile-money payments in the prototype

### 4. Direct institutional payment

Contributions are directed towards the **verified institution's official payment channel** rather than an individual's personal account.

This reduces the risk of funds being misdirected and creates a clearer connection between the donor, campaign, and beneficiary.

### 5. Confirmation and accountability

The institution can confirm receipt through its administrator portal and provide an official receipt or payment reference.

Donors can then track:

**Contribution → Payment → Institution → Confirmation → Receipt**

This creates a transparent record of the contribution.

### Fraud prevention

BillBridge reduces opportunities for fraud through:

* Verification of institutional beneficiaries.
* Matching campaigns to official institutional PayBills.
* Role-based institutional access.
* Transaction tracking.
* Institution-side confirmation.
* Official receipt/reference numbers.
* Campaign reporting mechanisms.
* Audit trails for important actions.

The objective is not to claim that fraud is impossible, but to make fraudulent collection **more difficult to carry out and easier to detect and investigate**.


## Technology Stack

| Layer                  | Technology                                                |
| ---------------------- | --------------------------------------------------------- |
| **Frontend**           | Next.js 16, React, TypeScript, Tailwind CSS, qrcode.react |
| **Backend**            | Next.js route handlers, Node.js                           |
| **Authentication**     | Signed-cookie sessions with donor and institution roles   |
| **Database**           | PostgreSQL + Prisma                                       |
| **Payments**           | Bitcoin Lightning via LNbits invoices                     |
| **Lightning → M-Pesa** | bitcoin.co.ke LNURL API                                   |
| **USSD & SMS**         | Africa's Talking                                          |
| **Exchange Rates**     | open.er-api.com and CoinGecko with caching/fallback       |
| **AI**                 | Anthropic Claude API with built-in glossary fallback      |
| **Sharing**            | WhatsApp integration                                      |

The prototype uses Prisma with PostgreSQL for persistent data management.


## Team

| Name                  | Role            |
| --------------------- | --------------- |
| **Doris Olela**       | Product Manager |
| **Beth Kinyanjui**    | UI/UX           |
| **Christine Kilonzo** | Frontend        |
| **Lucy Mwaura**       | Backend         |
| **Amy Wathira**       | Full-stack      |
| **Jael Bahati**       | Full-stack      |


## Repository & Links

* **Repository:** https://github.com/Waithira-amy/billbridge.git
* **Live Prototype:** billbridge-ten.vercel.app


### Local Setup

Clone the repository and install the dependencies:

bash
cp .env.example .env.local
npm install
npm run dev

The full setup and configuration instructions are available in the repository README.

## Status

### Working Prototype

BillBridge currently demonstrates the core fundraising and institutional verification flow.

### Implemented

* Campaign creation through the web interface
* USSD campaign handler
* Institution/PayBill verification
* PostgreSQL database
* Prisma data layer
* Donor dashboard
* Institution administrator portal
* Role-based access
* Transaction tracking
* Official receipt/reference functionality
* Multi-currency exchange-rate service
* Lightning invoice generation
* Lightning-to-M-Pesa demonstration
* AI help chatbot
* Impact tracker
* WhatsApp campaign sharing
* Feedback functionality
* USSD simulator

### Demo / Provider-Dependent Components

Some functionality remains dependent on production provider configuration, including:

* Live production Lightning settlement
* Production PayBill payout
* Production institution registry and verification
* Real USSD shortcode deployment
* Production SMS/OTP delivery
* Full institutional document-verification workflow


## Next Steps

1. **Complete production payment integration** for live Lightning payments and institutional PayBill payouts.
2. **Strengthen institution verification** using official institutional/business records and document verification.
3. **Deploy the USSD service** through a production shortcode and integrate SMS notifications.
4. **Strengthen authentication** using secure SMS/email one-time codes.
5. **Implement comprehensive audit logging** for campaigns, payments, confirmations, and administrative actions.
6. **Add stronger fraud detection** for suspicious campaigns, duplicate beneficiaries, unusual transaction patterns, and repeated complaints.
7. **Pilot with schools and healthcare institutions** to validate the platform with real users.
8. **Gather donor and institution feedback** and refine the user experience based on the pilot.
9. **Expand payment and currency support** as the platform grows.
10. **Continue developing the open-source project** with community contributions and documentation.

### Core Vision

> **BillBridge makes cross-border giving easier and more trustworthy by connecting donors directly to verified institutions through familiar payment channels, with Bitcoin Lightning providing the payment infrastructure underneath.**

