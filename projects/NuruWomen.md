# Nuru Women

## Overview

Nuru Women is a privacy-first women’s health knowledge and community platform designed for women in Kenya and across Africa.

It combines anonymous question asking, English and Kiswahili health-topic analysis, community knowledge, recent research, and research-gap visualization. The final hackathon build is deployed on Render and is available for public demonstration.

## Problem

Women often struggle to find health information that is reliable, understandable, private, and relevant to their local context.

Common challenges include health misinformation, limited access to specialists, stigma around reproductive and sexual health, language barriers, privacy concerns when asking sensitive questions, and major evidence gaps in women’s health across Africa.

## Solution

Nuru Women provides one place where users can ask sensitive health questions anonymously, explore women’s health information, browse recent research, and see where reliable evidence is still missing.

Key features include:

- Anonymous question submission without an account, email, or phone number
- Privacy scanning and redaction suggestions before publication
- English and Kiswahili support
- Safety-sensitive content checks
- Five core health areas: menstrual health, sexual and reproductive health, healthy ageing, postpartum health, and mental health
- Community questions published through Nostr
- Separate presentation of lived experience, clinical-response content, and evidence
- Searchable women’s health knowledge library
- Research catalogue with 20 references from 2020 onward
- Research-gap visualization using 265 country/topic rows across 53 African countries
- Kenya-focused health indicators
- Unified Docker deployment combining the frontend, Node gateway, and Python analysis service

Nuru Women is an educational and community platform. It does not replace professional medical advice, diagnosis, or emergency care.

## Technology Stack

**Frontend**
- React
- TypeScript
- Vite
- Tailwind CSS

**Backend**
- Node.js
- Express
- TypeScript

**AI and Analysis**
- Python
- FastAPI
- TF-IDF and logistic regression classification
- Privacy detection and redaction rules
- Safety analysis
- Topic classification
- Evidence retrieval
- English/Kiswahili routing

**Freedom Technology**
- Nostr
- Relay-based anonymous publishing
- One-time signing keys for public anonymous posts

**Data and Research**
- Women’s health research catalogue
- Evidence metadata
- Country/topic coverage datasets
- Kenya-focused health indicators
- Research-gap visualization

**Deployment**
- Docker
- Render
- GitHub

## Team

Nuru Women was developed collaboratively during Hack4Freedom Nairobi 2026 by contributors working across:

- AI / Machine Learning
- Data Science
- Frontend Development
- Backend Development
- Full-Stack Development
- UI / UX Design
- Cybersecurity and Privacy
- Research and Documentation

Development was coordinated through GitHub branches, commits, and pull requests so individual contributions could be reviewed and integrated into the final application.

## Repository & Links

**Live Platform:**  
https://nuru.shakespeare.wtf/

**GitHub Repository:**  
https://github.com/Ann20-dev/NuruWomen

## Status

The final Hack4Freedom deployment is now live on Render.

The current build includes:

- Working React frontend
- Node/Express gateway
- Python/FastAPI analysis service
- Anonymous question workflow
- Privacy, safety, language, and topic checks
- English and Kiswahili support
- Five core women’s health areas
- Nostr-based community publishing
- Searchable health knowledge library
- Research catalogue
- Research-gap dashboard across 53 African countries
- Kenya health-data visualization
- Integrated Docker and Render deployment

The frontend production build and backend build have passed validation, and production dependency audits returned no known vulnerabilities at the final validation checkpoint.

The current platform remains a hackathon-stage educational system. Automated privacy and safety checks can miss information, public Nostr posts may persist, and clinician identity verification is not yet implemented.

## Next Steps

Planned development includes:

- Add verified clinician workflows and human moderation
- Expand Kiswahili review and support more African languages
- Strengthen privacy and safety testing
- Expand the research and evidence library
- Improve evidence retrieval and citation
- Add more locally relevant African health datasets
- Improve decentralized Nostr identity and community features
- Explore appropriate Bitcoin and Lightning use cases
- Conduct user testing with women, clinicians, and community health workers
- Develop partnerships with health and research organizations
- Adopt a clear repository-wide open-source license
- Continue development through public GitHub contributions
