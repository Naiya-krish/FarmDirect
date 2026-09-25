# System Architecture & Technical Specifications

## 1. Tech Stack Overview
* **Frontend:** React Native / Expo (Mobile), React.js (Web Admin).
* **Backend:** FastAPI (Python), PostgreSQL, Redis Cache.
* **AI & NLP:** OpenAI Whisper (Speech-to-Text), Llama 3.
* **Logistics Routing Engine:** Google OR-Tools.

## 2. System Data Flow
`Farmer Voice Input` ➔ `Whisper NLP` ➔ `Price Recommendation Engine` ➔ `Marketplace Order` ➔ `OR-Tools Cluster Logistics`.

## 3. Core API Endpoint Specs

### 1. Parse Voice Audio
* **Endpoint:** `POST /api/v1/voice/parse`
* **Request:** Audio file payload.
* **Response:**
```json
{
  "crop": "Tomato",
  "grade": "Grade A",
  "quantity_kg": 200
}