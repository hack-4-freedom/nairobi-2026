SAUTI

Hack4Freedom Nairobi 2026

---

Overview

SAUTI is an open-source decentralized publishing platform designed to give independent authors greater control over their identity, publications, content distribution, and earnings.

The platform uses Nostr for decentralized author identity and publishing, and Bitcoin Lightning for direct micropayments between readers and authors.

Authors can create books, publish free or premium chapters, and allow readers to unlock premium content through Lightning payments.

---

Problem

Independent authors can face several challenges when publishing and monetizing their work:

- Limited access to traditional publishing opportunities
- Dependence on centralized publishing and content platforms
- Delayed or complicated royalty payments
- Unauthorized redistribution of digital publications
- Limited control over their digital publishing identity
- Difficulty receiving small direct payments from readers

These challenges can make it difficult for authors to independently publish their work and build direct relationships with their readers.

---

Solution

SAUTI provides a decentralized publishing platform where authors can publish and monetize their work while maintaining greater control over their digital identity.

The platform combines:

- Nostr for decentralized author identities and signed publishing events
- Nostr relays for distributing publication information across multiple independent relays
- Bitcoin Lightning for reader-to-author micropayments
- Free and premium chapters so authors can choose which content requires payment

A typical flow is:

1. An author connects a Nostr-compatible signer.
2. The author creates a book and adds chapters.
3. Chapters can be marked as free or premium.
4. Readers discover the book through the platform.
5. Readers pay a Lightning invoice to unlock premium content.
6. The author receives the payment and can track their earnings.

SAUTI does not attempt to make digital content completely impossible to copy. Instead, it focuses on giving authors greater control over identity, distribution, and direct monetization.

---

Technology Stack

- Python
- Flask — backend web framework
- HTML, CSS, JavaScript — frontend
- Bootstrap 5 — responsive UI
- Jinja2 — server-side templating
- PostgreSQL — database
- Nostr — decentralized identity and publishing
- Nostr Relays — decentralized content distribution
- Bitcoin Lightning — micropayments
- Git & GitHub — version control and open-source collaboration

---

Team

HerFreedom

Team members:

- Mackel Mboya — "@MboyaAkinyiMackel" (https://github.com/MboyaAkinyiMackel)
- Cherise Osambo — "@OsamboCherise" (https://github.com/OsamboCherise)
- Precious Muemi — "@PreciousMuemi" (https://github.com/PreciousMuemi)
- Fiona Gachuuri — "@FionaGachuuri" (https://github.com/FionaGachuuri)
- Donisia — "@donisia" (https://github.com/donisia)
- Bailey

---

Repository & Links

Project Repository:
https://github.com/donisia/her-freedom

Hack4Freedom Nairobi 2026:
https://github.com/hack-4-freedom/nairobi-2026

---

Status

SAUTI is currently in active development as a Hack4Freedom Nairobi 2026 project.

The web application structure and publishing interface are being developed, with Nostr identity, decentralized publishing, and Lightning payment functionality being integrated into the platform.

Some features are currently prototypes or planned components and may not yet be fully implemented.

---

Next Steps

- Complete Nostr signer integration
- Implement signed publishing events
- Connect the application to Nostr relays
- Complete PostgreSQL database integration
- Implement Lightning invoice generation
- Implement Lightning payment verification
- Automatically unlock premium chapters after verified payment
- Complete the author earnings dashboard
- Add testing for publishing and payment flows
- Deploy the application for public testing
