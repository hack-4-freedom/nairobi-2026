# SPILL

## Overview

Spill is an offline-first journalism and community platform designed for Africa, with a special focus on helping communities discover, share, and discuss local stories that may otherwise go unheard. The platform brings together storytelling, community engagement, and civic awareness in one accessible experience, making it easier for people to surface issues, track local narratives, and participate in public conversations even in low-connectivity environments.

The project is currently structured as a modern React + Vite frontend, built on Nostr, with a landing page and a community feed experience that showcases featured stories, community categories, and issue-based reporting.

---

## Problem

Many communities, especially in underserved or connectivity-constrained regions, lack a reliable way to document and share stories that matter to them. Traditional media ecosystems are often centralized, slow to respond, and disconnected from local realities. At the same time, community members often struggle to find a trustworthy, accessible place to discuss local issues, report developments, and engage in meaningful civic dialogue.

This creates a gap between local experiences and public visibility, limiting accountability, awareness, and community action.

---

## Solution

Spill provides a digital space where stories can be organized by community, interest, and issue. The app is designed to be offline-first, helping users access and engage with content even when internet access is unreliable or unavailable. The platform emphasizes community reporting, story discovery, and local visibility, giving residents a direct way to surface issues, participate in conversations, and keep communities informed.

The current interface includes:

- A landing page to present the mission and value proposition
- A community feed for browsing issue-based stories and updates
- Categorized content for different communities and reporting themes
- A clean and responsive UI built for mobile and web access
- A radio space for audio storytelling and voice transcription in multiple languages
- Self-hosting capabilities and decentralized architecture

---

## Technology Stack

The project is built using:

- **React 19** — Modern UI library for component-based development
- **TypeScript** — Type-safe JavaScript for better code quality and maintainability
- **Vite** — Next-generation build tool for fast development and optimized builds
- **CSS** — Custom styling for responsive and accessible design
- **HTML** — Base entry point and semantic structure
- **Lucide React** — Icon library for consistent UI elements
- **Nostr** — Decentralized protocol for event-based communication and message signing
- **LiveKit** — Real-time audio/video infrastructure for community radio and voice features
- **Cashu/eCash** — Private peer-to-peer micropayment system for contributor funding
- **Soapbox** — Social media-style client infrastructure

This stack allows for a fast, modular, and scalable frontend experience while keeping the project easy to run locally and maintain. The decentralized architecture via Nostr ensures community ownership and resilience.

---

## Project Structure
src/ ├── pages/ — Main app pages (landing, communities,..) ├── components/ — Reusable UI and page-specific components ├── data/ — Content and data definitions ├── styles/ — Styling layers, themes, and design tokens └── app/ — Application-level structure and wiring

---

## Team

Spill was created as part of the Hack4Freedom Nairobi 2026 initiative. The project reflects a collaborative approach to solving real community challenges using technology, design, and storytelling.

### **Shannon — Systems Architect & Protocol Lead**
- **Core focus:** Nostr protocol, P2P event signing schemas (NIPs), and offline-first state synchronization
- **Deliverables:** Protocol architecture, client relay connections, cryptographic key isolation, and technical documentation

### **Anne — Frontend Engineer (React & TypeScript)**
- **Core focus:** Client-side performance, local caching, and low-bandwidth UI responsiveness
- **Deliverables:** React + Vite application shell, IndexedDB/PWA service worker offline cache, and real-time feed rendering

### **Lucy — Payments & eCash Protocol Integration**
- **Core focus:** Private peer-to-peer micro-transactions, post tips, and spam prevention
- **Deliverables:** Lightning Network (WebLN/L402) and Cashu/eCash mint integration for anonymous contributor funding

### **Kelly — Product Designer & Threat Modeling Lead**
- **Core focus:** Operational security (OpSec) user journeys, accessible mobile interactions, and brand styling
- **Deliverables:** UI/UX system, high-contrast low-data visual assets, and secure whistleblower flow design

### **Lagat — QA, Security Testing & Documentation Lead**
- **Core focus:** Protocol verification, edge-case coverage, and relay latency benchmarking
- **Deliverables:** Test automation suites for cryptographic events, performance audits on 2G/3G speeds, and project documentation

### **Salma — Developer Advocate & Hackathon Demo Lead**
- **Core focus:** Submission narrative, use-case positioning, and showcase presentation
- **Deliverables:** Pitch script, recorded walkthrough video, and judging Q&A defense

---

## Getting Started

### Local Development

1. **Install dependencies:**
   ```bash
   npm install
   npm run dev

   Open the app:

Navigate to the URL shown in your terminal
Landing page: /
Community feed: /communities
Validation and Build
npm run typecheck
npm run build

### Current Status
The repository is in active early-stage development. The base product is already taking shape with:

A landing page introducing Spill's mission
A community feed interface for story discovery
Category-based content browsing and filtering
A front-end architecture ready for feature expansion
Radio functionality for audio storytelling
Nostr protocol integration for decentralized event handling
The project demonstrates the core vision and UX direction clearly, with a foundation ready for production expansion.

### Next Steps
Planned growth for the project includes:

User authentication and author profiles — Enable community members to own and manage their contributions
Story submission and content creation workflows — Empower communities to submit stories directly
Community moderation and trust systems — Build tools for community-led content curation and safety
Offline synchronization and local data persistence — Enhanced offline-first capabilities with full state sync
Richer reporting categories and search features — Better content discovery and filtering
Mobile-first improvements and accessibility enhancements — Optimized mobile experience and WCAG compliance
Full production deployment — Launch on production infrastructure with high availability
Analytics and community engagement tools — Track impact and measure community engagement

### Repository & Links
https://github.com/AnneAdhiambo/Spill


### Vision
Spill aims to evolve from a frontend prototype into a full civic storytelling platform for African communities. By combining offline-first technology, decentralized protocols, and community-centered design, Spill empowers residents to document, share, and act on the stories that matter most to them—regardless of connectivity, geography, or access to traditional media channels.

