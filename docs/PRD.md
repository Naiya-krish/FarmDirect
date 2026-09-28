# Product Requirement Document (PRD) — FarmDirect (v2.0)

## 1. Executive Summary
FarmDirect is a focused 6-week core B2B transaction engine connecting Farm Producer Organizations (FPOs) directly with local Kirana stores. It features Hindi voice-intake listing and automated Mandi price benchmarking.

## 2. Problem Statement
Smallholder FPOs struggle with complex UI mobile apps and lack real-time pricing data, leaving them vulnerable to under-pricing bulk produce. 
Simultaneously, local Kirana stores need direct bulk produce access without intermediary price inflations.

## 3. Target Audience (Single Persona Pair)
* **FPO Sellers:** Need rapid, hands-free listing in local Hindi dialect with pricing protection.
* **Kirana Buyers:** Need transparent, direct bulk ordering from nearby verified FPOs.

## 4. Rescoped MVP Features
1. **FPO Voice Listing:** Speech-to-text Hindi crop parsing via OpenAI Whisper.
2. **Mandi Price Bounds:** Automated dynamic price bounds via Agmarknet memory cache.
3. **Human-in-the-Loop Override:** FPO leads retain 100% control to adjust final pricing before posting[cite: 1].
4. **Kirana Bulk Orders:** Direct B2B REST order placement and inventory lock.

## 5. Core Value Metric
> Enables **1 FPO** to supply **50+ local Kirana stores** with verified bulk pricing