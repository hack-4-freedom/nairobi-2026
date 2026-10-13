# Safaripap

**Hack4Freedom Nairobi 2026**

---

## Overview

Safaripap lets passengers pay their matatu fare with ordinary M-Pesa, from their own phone, without handing it to anyone. Each fare settles instantly as Bitcoin over the Lightning Network into a wallet that belongs to that specific vehicle, the conductor sees it land on a live dashboard, and a public receipt is published to Nostr.

---

## Problem

Paying a matatu fare by M-Pesa today usually means showing your phone to the conductor so they can check the confirmation message.

- **Exposure:** the conductor sees the passenger's phone, balance and messages, which makes passengers easier targets for theft and scams.
- **Friction:** every fare is checked by eye, one passenger at a time, while the vehicle loads or moves.
- **Trust:** a message on a screen is easy to fake, and owners and SACCOs have no reliable record of what each matatu earned.

---

## Solution

- **Passengers** scan the QR sticker in the matatu (or type its code, or dial a USSD code on any phone) and approve the M-Pesa prompt on their own phone.
- **Bitika** converts the M-Pesa payment and sends it as sats to the vehicle's own Lightning Address on LNbits.
- **Conductors** sign in with the vehicle code and a PIN and see each fare arrive live, confirmed by a signed payment webhook rather than a screenshot. Only the last three digits of the passenger's phone and receipt are shown.
- **SACCO managers and matatu owners** sign in with their phone number and see fare totals by day and by vehicle, with a spreadsheet download.
- **Onboarding** a new matatu takes about a minute from the admin area: it creates the LNbits wallet and Lightning Address, the conductor login and a printable QR sticker. New SACCOs can ask to join from the website.
- **Transparency:** every paid fare publishes a receipt to Nostr relays, so SACCO totals can be checked independently.

---

## Technology Stack

- **App:** Next.js 14 (App Router), TypeScript, Tailwind CSS, installable as a PWA
- **Data:** Supabase (Postgres, Auth, Row Level Security, Realtime)
- **Payments:** Bitika (M-Pesa to Lightning)
- **Custody:** LNbits, one wallet and Lightning Address (LNURLp) per vehicle
- **Transparency:** Nostr (nostr-tools)
- **Feature-phone access:** Africa's Talking USSD
- **Hosting:** Vercel
- **Testing:** Vitest and React Testing Library

---

## Team

**Lady Lightning**

- Linnette — [@Linnnetteseven](https://github.com/Linnnetteseven)
- Rose Wachuka — [@ro61zzy](https://github.com/ro61zzy)
- Elizabeth Nanjala — [@Eliabethnanjala](https://github.com/Eliabethnanjala)
- Aisha Barasa — [@Aisha-Barasa](https://github.com/Aisha-Barasa)

---

## Repository & Links

- **Code:** https://github.com/Safaripap/safaripap
- **Live app:** https://safaripap.vercel.app

---

## Status

Working end to end in Bitika's sandbox:

- Passenger payments from the web app and over USSD
- Signed Bitika webhooks, including declined payments and failed payouts
- Live conductor dashboard with receipt search
- Per-vehicle LNbits wallets and Lightning Addresses
- Nostr receipts and live SACCO totals
- Admin onboarding with QR stickers, join requests, and the SACCO and owner dashboard

Switching to Bitika's live API key, so real fares move real sats, is in progress.

---

## Next Steps

- Go live with real M-Pesa payments and pilot with one SACCO and a few matatus
- Let owners withdraw a vehicle's sats to a Lightning wallet they control
- Add fare caps and per-route pricing set by the SACCO
- Grow the USSD flow and support Swahili in the app
