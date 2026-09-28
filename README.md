# FarmDirect

> **Team Name:** NexCode  
> **Team Members:** Ritika Singh, Krishnendu Naiya  
> **Tagline:** A Focused FPO-to-Kirana Direct B2B Produce Marketplace  

Traditional Indian agri-food supply chains suffer from excessive intermediary markups[cite: 3]. FarmDirect eliminates these friction points by enabling Farm Producer Organizations (FPOs) to list bulk produce directly to local Kirana store owners using a Hindi voice-intake engine with dynamic Mandi price benchmarking.

---

## 📌 Rescoped MVP Focus (Submission Revision v2.0)
Based on judge evaluation feedback, we executed a radical scope reduction to ensure full 6-week buildability:
* **Focused 1 Persona Pair:** FPO Sellers & Local Kirana Store Buyers[cite: 1, 2].
* **Core Tech Core:** Speech-to-Text Voice Listing (Whisper AI) + Agmarknet Mandi Price Benchmarking + B2B CRUD Orders[cite: 1, 2].
* **Dropped Secondary Scope:** Computer Vision (CV) produce grading, B2C urban consumer delivery, and OR-Tools complex routing heuristics[cite: 1, 2].

---

## 📄 Project Documentation

* **[Product Requirement Document (PRD)](./docs/PRD.md)** — Rescoped problem, single persona pair, and core B2B value metric.
* **[System Architecture & API Specs](./docs/ARCHITECTURE.md)** — Simplified data flow, PostgreSQL schema, and complete REST JSON schemas.
* **[UI/UX Screen Flows](./docs/UI_FLOW.md)** — Visual wireframe specs for voice-intake and B2B ordering.
* **[Execution Roadmap](./docs/ROADMAP.md)** — Feasible 6-week build plan.

---

## 🛠️ Tech Stack

* **Frontend:** React Native / Expo (Kirana & FPO App Screens)
* **Backend:** FastAPI (Python), PostgreSQL, Redis Cache
* **AI & NLP:** OpenAI Whisper (Hindi Voice Parsing & Entity Extraction)[cite: 1, 6]
* **Pricing Feed:** Dynamic Agmarknet API Benchmark Sync[cite: 1, 6]
* **Logistics:** Direct FPO Point Pickup