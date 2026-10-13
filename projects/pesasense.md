# PesaSense

**Hack4Freedom Nairobi 2026**

---

## Overview

PesaSense is a private, on-device financial profile for Kenya and a small **non-custodial** Bitcoin habit. From M-Pesa history, it shows a **safe surplus range** and lets users **approve each purchase**. Sats go to a **wallet they control**—pasted from apps like Blink or Wallet of Satoshi, or created **in the app** with Breez SDK Spark.

We also built a **chama ledger** for merry-go-round groups: it records who paid whom and **never holds** group funds. Each member pays the recipient from **their own** Lightning wallet.

Education, not financial advice. PesaSense does not hold user funds or private keys.

---

## Problem

Many Kenyans are curious about Bitcoin but unsure **how much is safe** to invest, whether products are trustworthy, or where to start. **M-Pesa** already contains rich payment history, yet most tools do not turn that into a clear surplus and buffer picture. **Trust** is fragile because of scams and volatility. **Chama** and informal circles need coordination without another party holding pooled money.

---

## Solution

- **Surplus & profile** — Show income, commitments, resilience, and a surplus range (floor / typical / ceiling). Users can paste **M-Pesa SMS** or upload a **statement PDF** on the device (`buildProfile()`), or try **demo profiles** (Amina, Brian). Overview includes a **money map** and life markers for the month.
- **Habit** — Save a monthly (or weekly) amount locally, with an optional **1st-of-month reminder** (notification only; no auto-debit). Every buy still needs explicit approval.
- **Invest** — **Bitika** on-ramp: M-Pesa → sats to the user’s Lightning address, with amount capped by surplus rules and explicit approval per purchase.
- **In-app wallet** — **Breez SDK Spark**: create/restore wallet, recovery phrase backup (copy + download file), balance, receive buys, withdraw in-app by paying `07…@bitcoin.co.ke` (KES via bitcoin.co.ke).
- **Chama** — Demo “Chama Sisters” flow: demo addresses record contributions only; real addresses trigger a Breez payment from that member’s wallet, then a ledger entry. Reliability notes are opt-in and stay on the device.
- **Privacy** — Encrypted profile save with Nostr (NIP-44); keys and raw statements stay on the device.

---

## Technology Stack

- TypeScript, pnpm monorepo, Vitest
- Next.js (App Router), PWA, Tailwind CSS
- M-Pesa SMS + PDF parsing and financial profile engine (`packages/core`)
- Bitika API (on-ramp) — `packages/wallet` + Next.js API routes
- Breez SDK Spark (in-browser Lightning wallet, WASM)
- Chama ledger — `packages/nostr` (nostr-tools, NIP-78)
- USSD menu (`packages/ussd`) sharing the same purchase rules as the web app
- Hosting: Vercel

---

## Team

- Immaculate Munde — Blockchain development (invest, wallet creation, withdraw)
- Mercy Wairimu — Blockchain development (chama ledger ans USSD)
- Blessings Wanjiku — Frontend development and UI/UX
- Leonida Jeptoo - Backend development
- Gathoni Karume - Product Manager

---

## Repository & Links

- **Code:** [https://github.com/immaculate-munde/hack4freedom](https://github.com/immaculate-munde/hack4freedom)
- **Live demo:** [https://pesasense.vercel.app](https://pesasense.vercel.app)
- **Run locally:** `pnpm install` → copy `apps/web/.env.example` to `apps/web/.env.local` → set `BITIKA_API_KEY` (sandbox `bk_test_…`) and `NEXT_PUBLIC_BREEZ_API_KEY` → `pnpm dev` → [http://localhost:3000](http://localhost:3000)
- **Suggested demo path:** [welcome](https://pesasense.vercel.app/welcome) → onboard or demo profile → overview → habit → invest (Bitika sandbox) → wallet / chama

---

## Status

**Built**

- Onboarding with SMS/PDF import and demo profiles; surplus overview and learn content
- Habit save and local reminder; invest flow with Bitika (sandbox; live key path wired)
- Breez in-app wallet with seed backup; device purchase history
- Chama pay-and-record flow; Bitika webhook handler; encrypted Nostr profile save
- Automated tests (`pnpm test`)

**Known limits**

- Some Safaricom PDF exports parse incompletely; SMS paste is the most reliable import for demos
- Bitika **sandbox** simulates M-Pesa and may not fund a real wallet; full withdraw needs real sats or a successful live buy
- Live Bitika collect may require merchant enablement on Bitika’s side

**In progress**

- Stronger PDF ingest across export variants; fuller education and scenario modules
- Durable hosting for purchase/USSD state; partner and regulatory copy verification

---

## Next Steps

- Improve real statement ingest and profile quality checks for production PDFs
- Persist wallet and purchase activity in a durable store on the host
- Production Bitika webhooks and user testing with parsed imports
- Optional: connect external wallets (e.g. NWC) alongside Breez

