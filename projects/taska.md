# Taska

**Hack4Freedom Nairobi 2026**

---

## Overview

Taska helps AI startups and chatbot builders test whether their AI actually understands the people they are building for.

A company can send us a small number of AI responses and choose the language and situation they want tested.

People who understand that language and context then check the responses. Another person reviews their work, and the company gets the results.

**Company → Evaluator → Reviewer → Results**

We are starting with African languages and local situations because AI can sometimes sound correct while still getting the meaning wrong.

Taska also uses Bitcoin Lightning to make it easier to pay people for these small pieces of work.

---

## Problem

AI is being used more and more across Africa, but it does not always understand how people actually speak or communicate.

For example, an AI might:

- Give a Swahili answer that sounds unnatural
- Understand the words but miss the meaning
- Give an answer that does not fit the local situation
- Work well in English but poorly in an African language

A small AI startup may only need 20, 50, or 100 responses tested. Finding the right people to test them quickly can be difficult.

There is also the problem of paying people for small amounts of work. Sending very small payments across countries can be expensive or inconvenient.

---

## Solution

Taska makes it simple for AI builders to get their responses tested by people who understand the language and situation.

### How it works

**Company**

The company sends AI responses to Taska and chooses what they want tested.

**Evaluator**

An evaluator checks the response:

- Is it correct?
- Does it sound natural?
- Does it make sense in this situation?

If the answer is wrong, they can explain what should be changed.

**Reviewer**

Another person checks the evaluation before it is sent back to the company.

**Company**

The company gets the results and can see where its AI needs improvement.

### Bitcoin Lightning

The work can be very small. An evaluator might only earn a few cents or a small amount for checking a few responses.

Taska uses **Bitcoin Lightning** to make these small payments easier and faster.

Companies do not have to use Bitcoin to use Taska. They can pay Taska normally, while Taska can use Lightning to pay the people doing the work.

We also give companies an incentive, ie a 10% discount , when they choose to pay through Lightning.

---

## Technology Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 16, App Router, Server Actions |
| UI | React 19, Tailwind CSS 4 |
| Language | TypeScript |
| Database | PostgreSQL, Prisma 6 |
| Local Database | PGlite |
| Production Database | Neon |
| Authentication | Auth.js, JWT sessions, bcrypt |
| Validation | Zod 4 |
| AI | OpenAI-compatible API |
| Payments | Bitcoin Lightning via Breez SDK Spark |
| Hosting | Vercel |
| Code | GitHub |

---

## Team

### Leadership

- **Florence Makaa** — Team Lead
- **Stacy Kweto** — Project Manager

### Front-end + UI/UX

- **Winfred Silii** — Front-end
- **Hellen Anyango** — Front-end + UI/UX

### Back-end

- **Mitchelle Ashimosi** — Back-end
- **Hadassah Ndonyi** — Back-end

### AI

- **Becky Gabrielle** — AI

---

## Repository & Links

**GitHub:**  
https://github.com/rxymitchy/taska

**Live Demo:**  
https://taska-beta.vercel.app

---

## Status

- Core platform is functional
- AI evaluation workflow is working
- Bitcoin Lightning payments are live through Breez SDK Spark
- Users can receive payments as they complete evaluation tasks
- Authentication and database features are being refined
- The project is currently in beta
---

## Next Steps

- Expand support for more African languages and local language varieties
- Improve evaluator matching and task assignment
- Refine the evaluation and review process
- Improve company-facing reports and feedback
- Add support for more AI models and APIs
- Support larger evaluation batches for companies
- Improve the platform based on feedback from early users
- Explore an API for companies that want to run evaluations automatically

In the long run, we want Taska to make it easy for AI builders to answer one simple question:

> **Does my AI actually understand the people I'm building it for?**
