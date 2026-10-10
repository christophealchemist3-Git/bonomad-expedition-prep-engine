# BoNomad – Expedition Prep Engine

**AI-powered expedition planning for off-road and overland travel.**

BoNomad is a functional prototype designed to explore how AI can simplify the preparation of off-road expeditions and overland journeys by combining vehicle constraints, itinerary planning and contextual recommendations.

The project takes a product-oriented approach to AI, turning complex travel requirements into a structured and personalized planning experience.

## The Challenge

Preparing an off-road expedition involves more than selecting a destination. Travellers must consider vehicle capabilities, terrain, autonomy, route constraints, logistics and preparation requirements.

BoNomad brings these elements together in a more coherent and user-friendly experience: the user describes their trip and vehicle, and the platform generates a tailored roadbook.

## Key Capabilities

- Personalized expedition planning based on user requirements and vehicle characteristics
- Itinerary generation for off-road and overland travel
- Contextual recommendations to support trip preparation
- Expedition readiness through structured preparation and checklists
- GPX export for use in navigation devices and apps
- Equipment recommendations with affiliate links
- Credits system and waitlist

## Product Demonstration

**Live platform:** [Open the live demo](https://roadbook-five.vercel.app/)

The platform is a prototype. Features and capabilities should be understood in the context of its current development stage.


## Screenshots

<img width="800" alt="BoNomad Home Page" src="https://github.com/user-attachments/assets/1f2051ce-95d5-46a1-ae6a-036425a67f6e" />

<img width="800" alt="BoNomad Home Page 2" src="https://github.com/user-attachments/assets/257c3a47-25e5-42d5-bde0-2993c12baaf5" />

<img width="800" alt="BoNomad Home Page 3" src="https://github.com/user-attachments/assets/1dd3c111-0d2f-496a-a65e-97c070f950fd" />

<img width="2502" height="800" alt="BoNomad Home Page4" src="https://github.com/user-attachments/assets/6bbc9b36-2f8b-4f88-90d5-c13bed841b0d" />


## Technology Stack

| Layer | Technologies |
|---|---|
| **Frontend** | Next.js 16 (App Router), React 19, TypeScript 5 (strict), Tailwind CSS v4, Framer Motion |
| **Backend & Data** | Supabase (PostgreSQL, Auth, Row Level Security), Server Actions & Route Handlers |
| **AI** | Anthropic Claude API (Messages) for itinerary generation |
| **Mapping** | Mapbox GL JS, react-map-gl, Leaflet |
| **UI** | Custom design system, Tailwind CSS, react-hot-toast |
| **Quality & Tooling** | ESLint 9, Node.js 20+ |
| **Deployment** | Vercel, GitHub |

## Product & Technology Approach

The project combines product design, functional requirements, AI use cases and iterative prototyping. Technical choices are guided by the objective of building a usable, evolvable and user-oriented experience, while keeping AI costs and response times under control.

## Challenges & Learnings

### Building a full platform end to end in 3 months

BoNomad was designed and built end to end in three months: product definition, UX, database and authentication, AI integration, mapping, deployment. The main challenge was making product, design and technical decisions quickly while keeping the architecture clean enough to evolve.

### A cost-efficient AI generation pipeline

Calling an LLM for every request is slow and expensive. A significant part of the work went into designing a multi-layer caching logic so that the AI is only called when truly necessary.

Each generation request follows this order:

1. **Parameter hashing**: the trip parameters (normalized destination, duration, season, vehicle, terrain, difficulty, objective, and rounded risk / comfort / isolation sliders) are reduced to a deterministic SHA-256 hash. Only the parameters that meaningfully change the itinerary are included, not every form field.
2. **Exact cache**: if an identical trip has already been generated, the stored roadbook is returned instantly, with no AI call. A hit counter tracks reuse.
3. **Cluster match**: if no exact match exists, the system looks for a similar trip (same destination, vehicle type and difficulty) within a cluster of already generated itineraries. If the cluster is mature enough, its representative roadbook is reused, again without an AI call.
4. **AI generation**: only when both layers miss, Claude generates a new itinerary. The result is then saved to the cache and added to its cluster, so future similar requests benefit from it.

This approach reduces API costs and latency, and the platform becomes more efficient as usage grows.

## My Contribution

- Product vision and use-case definition
- Functional design and user journey definition
- AI opportunity identification and integration approach
- Full-stack development, from database schema to AI pipeline
- Technology selection and prototype development
- Iterative testing and refinement

## Current Status

BoNomad is an ongoing prototype used to explore the practical application of AI to expedition planning. Future improvements may include enhanced route intelligence, richer contextual data and more advanced personalization.

## Contact

[Christophe Marechal] · [www.linkedin.com/in/christophe-marechal-5296615]

## Intellectual Property

© 2026 BoNomad – Expedition Prep Engine. All rights reserved.

This repository is provided for portfolio and demonstration purposes only. No license is granted to use, copy, modify, distribute or commercially exploit its original content without prior written permission from the rights holder.
