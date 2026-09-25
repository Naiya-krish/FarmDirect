# System Architecture & Technical Specifications

## 1. Tech Stack Overview
* **Frontend:** React Native / Expo (Mobile), React.js (Web Admin)[cite: 3].
* **Backend:** FastAPI (Python), PostgreSQL, Redis Cache[cite: 3].
* **AI & NLP:** OpenAI Whisper (Speech-to-Text), Llama 3[cite: 3].
* **Logistics Routing Engine:** Google OR-Tools[cite: 3].

## 2. System Data Flow
`Farmer Voice Input` ➔ `Whisper NLP` ➔ `Price Recommendation Engine` ➔ `Marketplace Order` ➔ `OR-Tools Cluster Logistics`[cite: 3].

## 3. Core API Endpoint Specs

### 1. Parse Voice Audio
* **Endpoint:** `POST /api/v1/voice/parse`[cite: 3]
* **Request:** Audio file payload[cite: 3].
* **Response:**
```json
{
  "crop": "Tomato",
  "grade": "Grade A",
  "quantity_kg": 200
}