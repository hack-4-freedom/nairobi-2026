# Sauti

**Hack4Freedom Nairobi 2026**

---

## Overview

Sauti means “voice” in Swahili.

It is a publishing platform for writers who cannot safely put their real name on their work. A book that criticises the government, the police, the church, or a powerful family is often not answered with an argument. It is banned. The writer can lose a job, a publisher, or their freedom.

Sauti gives that writer a **pseudonymous identity**. They publish under a pen name tied only to a Nostr key they hold. Readers pay the pen name — in sats over Lightning, or in Kenyan shillings over M-Pesa. Sauti never asks for an ID, an email, or a private key.

**Your voice. Your story. Your freedom.**

The demo library is African literature: reading companions to writers whose books were banned, seized, or written from prison, including Chinua Achebe, Wole Soyinka, Ngũgĩ wa Thiong’o, Nadine Gordimer, and Nawal El Saadawi.

---

## Problem

Authors do not have the freedom to write about anything.

If they name corruption, question the state, or tell a story the official version does not allow, the book can be:

- banned by the government, or stopped at the border
- taken off Amazon, a bookshop, or a school list
- unpaid, because the bank or M-Pesa number is in their legal name
- used against them, because the name on the cover is a home address

Centralised platforms make this worse. The login is the identity. The payout is the identity. One complaint or one “terms of service” change and both the book and the money are gone.

So writers stay quiet, use a weak alias that is still tied to a phone number, or leave the country. Readers in Kenya who want to support that work often cannot pay without a card or a foreign account.

---

## Solution

Sauti separates the voice from the legal person.

**Pseudonymous identity.** The public author is a pen name. The real account is a Nostr key that never leaves the writer’s device. Sign in with a NIP-07 extension (Alby, nos2x) or a demo key. We will never ask for an nsec.

**No real-name publishing.** There is no email, national ID, or “legal name” form. A writer criticising a government does not have to give that government a customer record.

**Work that one company cannot delete.** Books and chapters are signed as Nostr events (NIP-23) and can be sent to many relays. Taking the website down does not un-write the book.

**Pay the pen name, not the passport.** A reader unlocks one chapter, or pays a monthly subscription that opens every paid chapter by that author for 30 days. Payment is Lightning (sats) or M-Pesa (KES). The money is meant to go to the author, not sit in a platform account.

**The library is the argument.** The catalogue is built around African books that were banned or written under threat, so the product shows why a pen name is not a gimmick.

The hackathon build is a working demo: browse, unlock, subscribe, and see earnings, all under names the writers chose.

---

## Technology Stack

- Frontend: React 18, Vite, Tailwind CSS, React Router
- Backend: Flask, Flask-SQLAlchemy, SQLite
- Identity: Nostr (NIP-07, NIP-23, NIP-98). Public key only.
- Payments: Lightning (mock or a real node) and M-Pesa Daraja STK Push (mock by default)
- Tests: pytest

---

## Team

- Donisia Muthiani

---

## Repository & Links

- Code: add your public GitHub repo URL here after you push the project
- Local demo: frontend at http://localhost:5173/ — API at http://127.0.0.1:5000/

---

## Status

Working hackathon demo. Readers can browse the library, pay with Lightning or M-Pesa (simulator in demo mode), subscribe for a month, and read unlocked chapters. Authors can connect a signer, publish under a pen name, and see what they earned.

Not ready for production. Live M-Pesa needs Daraja credentials and a public callback URL. Live Lightning needs a real node. Some demo covers are publisher artwork and should be replaced before a public launch. A pen name only protects a writer as far as their own operational security — the software does not make anyone invisible.

---

## Next Steps

- Put the code on a public GitHub repository with an MIT license
- Turn on real M-Pesa and Lightning when credentials are available
- Let authors set their own subscription price and Lightning address
- Use only author-owned or original cover images
- Deploy a public demo
- Keep logs from tying a pen name to an IP or phone number, except where M-Pesa itself requires a number to send the prompt
