# RESILIENCE
Hack4Freedom Nairobi 2026

## Overview

A privacy-first, pseudonymous web platform designed to help people experiencing gender-based violence find support, connect with trusted people and resources, and maintain greater control over the information they share.

## Problem
People experiencing gender-based violence can face significant barriers when trying to seek help.

Many digital platforms begin with questions such as:

What's your name?
What's your phone number?
What's your email?
Where are you located?

For someone in a sensitive or potentially unsafe situation, providing personal information can create an additional privacy concern.

At the same time, support may be fragmented across counselors, peer communities, legal and medical resources, shelters, and financial assistance.

This creates several challenges:

Privacy: Sensitive support-seeking activity can expose personal information.
Trust: People need confidence that the person or organization they are interacting with is legitimate.
Control: Users should have meaningful control over what information they share.
Access: Support should remain useful when connectivity is limited.
Fragmentation: Relevant support and resources may exist in different places.
Safety: A support platform must consider what information it stores, where it goes, and what happens if a device or account is compromised.

The question we are exploring:

Can we design a support platform where privacy and user control are part of the architecture from the beginning, rather than features added afterwards?

## Solution
Resilience provides a privacy-first entry point to support.

Instead of making personal identity the starting point, the platform starts with the person's need for support.

The experience

1. Enter safely

The user accesses Resilience through a safety-conscious web experience.

2. Create a pseudonymous identity

The user can interact without making their real-world identity a mandatory part of the experience.

3. Choose what they need

They can explore different forms of support, such as:

Counseling
Peer support
Legal resources
Medical resources
Shelter
Other support services

4. Find and connect

The user can discover relevant counselors, communities, and resources.

5. Communicate

Resilience is designed around privacy-conscious communication and decentralized technologies.

6. Stay in control

The platform aims to minimize unnecessary data collection and give the user greater control over sensitive information.

Privacy by design

The core philosophy is:

Collect less. Protect more.

Rather than treating privacy as only a security feature, Resilience considers privacy throughout the product architecture.

This includes exploring:

Pseudonymous identities
Local handling of sensitive information
Encrypted communication
Decentralized communication infrastructure
Offline-aware workflows
User-controlled data
Privacy-conscious notifications and safety controls
Counselor verification

Resilience does not position itself as the professional licensing authority.

The design allows trusted external organizations to provide verification or attestations. Resilience can then validate and display relevant verification states, such as whether an attestation is valid, expired, or revoked.

This separates professional verification from the platform itself.

## Technology Stack
Frontend - React Native
Backend - Python3
Database - SQL Lite

Decentralized communication
Nostr for decentralized communication and event-based interactions
Privacy-conscious encryption approaches
Relay-based communication

Nostr is not treated as a magic anonymity layer. The project recognizes that decentralized communication can still expose metadata and that browser, device, relay, and network security must also be considered.

Payments

Bitcoin Lightning
Lightning-compatible wallets
Zap/payment flows

The payment architecture is designed around non-custodial interaction rather than making Resilience the user's financial custodian.

Security & privacy
Security considerations include:

Pseudonymous identity
Local handling of sensitive information
Encryption
Minimal data collection
Privacy-conscious logging
Session and account safety
Quick-exit and local-data clearing concepts
Protection against common web threats

## Team
1. Vanessa Kalondu - UI/UX Designer
2. Adreen Nyawira Githinji - Frontend Developer
3. Wambugu Jane Rose Muthoni - Project Manager and Quality Asurance 
4. Nelly Nakhero - Full Stack
5. ⁠Mona Tanei - Backend and Deveops
6. Grace Mugoiri - Backend developer
7. Daisy Sawe - Fullstack

## Repository & Links
Code: https://github.com/grace-mugoiri/Resilience
Live demo: https://nostrresilience.vercel.app/
Design

## Status
Resilience is currently a working prototype / proof of concept demonstrating the core product experience and architectural direction.

Currently demonstrated
Responsive web application experience
Survivor-oriented onboarding and support journey
Counselor-oriented experience
Pseudonymous identity concept
Support and resource discovery
Counselor profiles
Privacy and safety-oriented interface
Backend/API foundation
Architecture prepared for decentralized communication and Lightning-based support
Prototype integrations

Some integrations are currently represented through mocked or prototype implementations rather than production infrastructure.

These include areas such as:

Nostr communication
External counselor verification
Lightning wallet/payment integration
Sensitive health-data workflows
Certain backend services

This allows the team to demonstrate the intended user experience and technical architecture while clearly separating the current prototype from production-ready infrastructure.

Important limitation

Resilience does not claim to provide absolute anonymity or eliminate every privacy risk.

A web application can still be affected by browser security, device compromise, network metadata, relay metadata, screenshots, browser history, malicious extensions, and other factors outside the application's direct control.

These are considered part of the project's security and future engineering work.

## Next Steps
1. Strengthen privacy and security
2. Implement decentralized communication
3. Implement counselor verification