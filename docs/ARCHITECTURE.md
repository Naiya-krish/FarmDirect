# System Architecture & Technical Specifications (v2.0)

## 1. Simplified Tech Stack
* **Frontend:** React Native (Mobile App)[cite: 1, 6]
* **Backend:** FastAPI (Python), PostgreSQL, Redis Cache[cite: 1, 6]
* **Speech NLP:** OpenAI Whisper (Hindi Audio Processing)[cite: 1, 6]
* **Price Cache:** Agmarknet API -> Redis Memory Cache[cite: 1]

## 2. Core System Data Flow
`Voice Audio Ingestion` ➔ `Whisper + Regex Entity Parsing` ➔ `Agmarknet Redis Lookup` ➔ `FPO Manual Review & Publish` ➔ `Kirana Order Creation & Atomic Stock Lock`[cite: 1].

---

## 3. PostgreSQL Database Schema

```sql
-- Users Table
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    role VARCHAR(20) CHECK (role IN ('FPO', 'Kirana')),
    phone VARCHAR(15) UNIQUE NOT NULL,
    location_point VARCHAR(255) NOT NULL
);

-- Listings Table
CREATE TABLE listings (
    id SERIAL PRIMARY KEY,
    fpo_id INT REFERENCES users(id),
    crop_name VARCHAR(100) NOT NULL,
    total_qty_kg INT NOT NULL,
    price_per_kg NUMERIC(10, 2) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Orders Table
CREATE TABLE orders (
    id SERIAL PRIMARY KEY,
    listing_id INT REFERENCES listings(id),
    kirana_id INT REFERENCES users(id),
    order_qty INT NOT NULL,
    status VARCHAR(20) DEFAULT 'CONFIRMED',
    pickup_slot VARCHAR(100) NOT NULL
);