# RESILIENCE
> A privacy-first, pseudonymous pwa platform designed to help people experiencing gender-based violence find support, connect with trusted people and resources, built on Nostr and Lightning, with M-Pesa payouts for counselors and grants.

---

## Overview

Resilience is a Progressive Web App (PWA) that lets a survivor reach verified counselors, trusted local resources, and financial support **without handing over their identity**.

- **Pseudonymous accounts.** No phone number or email. Each account is a Nostr keypair generated on the person's device and unlocked with a PIN.
- **End-to-end encrypted conversations** between survivors and counselors, in small circles, and in support groups.
- **Verified counselors.** A partner organization reviews credentials privately and signs an attestation. Survivors see only "verified", never documents or legal identity.
- **Resource directory.** Shelters, legal support, medical services and rights information, with offline bundles.
- **Grants and payouts.** Lightning-based wallet flows, settled to counselors and recipients through M-Pesa in KES.
- **Safety by design.** Guest mode, one-press Exit with auto-lock, generic push notifications, and honest wording about what "delete" can and cannot do.

---


## Problem

Survivors of abuse need someone safe to talk to, trustworthy local resources, and sometimes money to leave a dangerous situation. The tools they have today often work against them:

- **Identity-linked apps.** Phone-number-based messengers tie conversations to a real identity. An abuser who gets brief access to a phone can often see who the survivor has been talking to.
- **Centralized message storage.** A breach, legal demand or insider can expose private conversations.
- **Unverifiable counselors.** Survivors cannot tell a qualified counselor from a bad actor, and organizations cannot verify counselors without collecting sensitive documents.
- **Traceable money.** Support funds usually move through channels that leave a visible trail, and payment relationships can themselves be dangerous to reveal.
- **Metadata.** Even when content is encrypted, *who talks to whom* and *who looked at which shelter* can be enough to put someone at risk.
- **Disconnected Access**: Survivors especially in poorly connected areas lack access to meaniningfull access when connectivity is limited.
- **Fragmentation**: Relevant support and resources may exist in different places.
- **Safety Concerns**: A support platform must consider what information it stores, where it goes, and what happens if a device or account is compromised.

---

## Solution

Resilience splits responsibilities so that no single component holds everything.

| Layer | Responsibility |
|---|---|
| **Device (PWA)** | Keys, PIN, backup words, plaintext messages, guest sessions, private records. All encryption happens here. |
| **Nostr protocol** | Signed identities, encrypted messaging, counselor attestations, invitations, wallet communication |
| **Private relays** | Store-and-forward encrypted events, offline delivery, access control, short retention, rate limiting |
| **Backend (FastAPI + PostgreSQL)** | Credential review, resource directory, abuse handling, grants, internal KES ledger, M-Pesa payouts, generic push notifications |

```text
Resilience PWA
  ├── Local encrypted vault      keys, PIN, records, cached messages
  ├── Nostr protocol layer       NIP-17 + NIP-44 + NIP-59
  ├── Private Resilience relays  encrypted delivery, ACLs, expiration
  └── Resilience API
        counselor review · resource directory · reporting
        grants and ledger · Lightning / M-Pesa · push notifications
```

### Key design decisions

- **Private keys never leave the device.** The API and relays never receive survivor or counselor private keys, backup words, or PINs.
- **Metadata-reducing messaging.** Private conversations use NIP-17 with NIP-44 encryption and NIP-59 gift wrapping. Every message gets a fresh random wrapper key, so relays see only an encrypted envelope addressed to a recipient.
- **Dedicated private relays, not public ones.** Two relays for availability, authenticated with NIP-42, with restricted queries, event-kind allowlists and short retention.
- **No public zaps.** NIP-57 receipts reveal who paid whom, which is the wrong default for survivor payments. Wallet commands use NIP-47 (Nostr Wallet Connect) between Resilience and an organization-controlled wallet.
- **Counselor verification without exposing documents.** Credential files go to encrypted organization-controlled storage, never to relays. The organization signs an attestation with no legal name, document hash or license number. Clients check the signature, the trusted-organization registry, expiry and revocation before showing a badge.
- **Guest mode.** A fresh ephemeral keypair per visit, short NIP-40 expiry tags, and local deletion on Exit.
- **Small circles, private groups.** Circles are capped at three members, with no searchable directory. Support groups are enforced at the private relay with application-level encryption, never public Nostr channels, and encryption state rotates whenever membership changes.
- **Honest security claims.** A four-digit PIN is a convenience lock, not a strong secret. Vault keys are also protected by a device-bound non-extractable key, and the UI never claims a PIN alone resists a capable offline attacker. Deleting locally does not delete copies held by recipients or relays, and the app says so.

### Safety design documents

We wrote these before the code, because the choices in them are hard to undo later:

- **Threat model and event design:** protected assets, trust boundaries, attacker scenarios, data-placement rules, the encrypted payload catalogue, relay policy requirements, and acceptance criteria for the first messaging milestone.
- **Key-management design:** key inventory and lifecycle, PIN and vault key hierarchy, backup and restore, guest keys, organization key hierarchy, rotation, revocation and compromise handling, and browser hardening (strict CSP, no third-party scripts).

---


## Technology Stack

| Area | Technology |
|---|---|
| Freedom tech | **Nostr** (NIP-01, 17, 40, 42, 44, 47, 59; NIP-98 for HTTP auth; NIP-06 or NIP-49 for backup, still to be decided), **Lightning**, **M-Pesa** |
| Frontend | Progressive Web App; local encrypted vault in IndexedDB; Web Crypto (device-bound keys), audited Nostr/secp256k1 library, Argon2id for the PIN KDF |
| Backend | Python, FastAPI, `nostr-sdk` for relay connections and event verification |
| Data | PostgreSQL (operational state and the authoritative ledger, never decrypted conversations) |
| Relays | Two private relays (`strfry` as the starting point) with NIP-42 authentication and custom admission and query policies |
| Storage | S3-compatible encrypted private bucket for counselor credentials, with short-lived signed upload URLs |
| Workers | Background worker (Celery/Redis, Dramatiq or ARQ) for relay subscriptions, retries, expirations, notifications, and payment reconciliation |
| Notifications | Web Push (VAPID) with generic content only |
| Infrastructure | Docker Compose for local development; KMS/HSM and a secrets manager for organization and service keys |

---

## Team

| Name | Role | GitHub |
|---|---|---|
| Vanessa Kalondu | UI/UX Designer | Vankalondu |
| Adreen Nyawira Githinji | Frontend Developer | Adreen-99 |
| Wambugu Jane Rose Muthoni | Project Manager and Quality Asurance  | Mujojo03 |
| Nelly Nakhero | Full Stack Developer | nellynakhero |
| Mona Tanei | Backend and DevOps | ⁠taneiii |
| Grace Mugoiri | Backend developer | grace-mugoiri |
| Daisy Sawe | Fullstack Developer | sawe-daisy |

## Repository & Links

| Part | Link |
|---|---|
| Backend (`Dev` branch) | https://github.com/grace-mugoiri/Resilience/tree/Dev |
| Frontend (`frontend` branch) | https://github.com/grace-mugoiri/Resilience/tree/frontend |
| Design | https://www.figma.com/design/C7ag3vSbPMNlPGSUsdR35b/Resilience-Project--Copy-?node-id=0-1&p=f |
| Doccumentation | https://github.com/grace-mugoiri/Resilience/blob/Dev/README.md |
| Demo / video | TODO |

### Running the backend locally

```bash
cd backend
cp .env.example .env

python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements-dev.txt

# generate a development platform key and signed config,
# then copy the printed PLATFORM_PUBKEY=... into backend/.env
python scripts/sign_config.py --dev

docker compose up --build
```

Two relays start at `ws://localhost:7777` and `ws://localhost:7778`. Full setup, tests and troubleshooting are in `backend/README.md`.

---

## Status

**Where we are:** Resilience is currently a working prototype with the proof of concept coded demonstrating the core product experience and architectural direction.

> TODO: tick only what you can demonstrate.

**Design**
- [x] Threat model and Nostr event design
- [x] Key-management design (key inventory, vault hierarchy, backup, rotation, revocation)

**Backend and relays**
- [x] FastAPI backend with Docker Compose and two local relays
- [x] Platform key and signed config script (`scripts/sign_config.py --dev`)
- [x] NIP-42 authentication challenge issued by relays
- [x] Real cryptographic event validation through `nostr-sdk` (event ID, Schnorr signature, kinds, tags, size, timestamps), replacing the placeholder validator

**Frontend (PWA)**
- [x] Client-side key generation and PIN-encrypted vault
- [x] Backup words and restore, fully on-device
- [x] Auto-exit, lock, and clear-device behavior

**First vertical slice (the milestone that matters most)**
- [x] Survivor generates an identity, sends an encrypted NIP-17 message, both relays accept it, and the counselor decrypts it, with neither relay nor backend able to read it

**Work In Progress**
-  M-Pesa payouts

### Known limitations

We list these deliberately:

- NIP-44 has documented limits around metadata hiding, forward secrecy and post-compromise security in relay-based messaging. We are not claiming Signal-equivalent guarantees.
- We cannot guarantee deletion of messages already received by another participant or retained by a relay.
- Confidentiality does not hold on a compromised or unlocked device, and we cannot prevent screenshots by a participant.
- IP and timing metadata are only partly mitigated, and we make no network-anonymity claim.
- Because keys live in the browser, cross-site scripting while the vault is unlocked equals key compromise. This is why the design requires a strict CSP and no third-party scripts.
- **A professional threat-model and encryption review is required before any real survivor or real credentials use this system.**

---

## Next Steps

Ordered so identity and private messaging, which everything else depends on, come first.

1. **Complete the messaging vertical slice** with automated tests for tampering, replay, expiry, oversized events, duplicate delivery from two relays, and guest-key deletion.
2. **Deploy two private relays** with TLS, NIP-42, restricted queries, retention policies, monitoring and backups.
3. **Mpesa integration:** M-Pesa payouts, idempotency and reconciliation.
4. **Kenya pilot:** one partner organization and a small cohort of counselors, with legal and safeguarding input on credential retention and payment-key custody.
5. **Independent security review and hardening** before production keys or real credentials are used.
