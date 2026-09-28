# UI/UX Screen Flows & Wireframe Specs (v2.0)

## 🎨 Interactive Miro Board & Visual Wireframe Specs

> **🌐 Live Interactive Board:**  
> [👉 **Click Here to View the FarmDirect B2B UX Miro Board Live**](https://miro.com/app/board/uXjVHhK4fe4=/?share_link_id=31771691371)

![FarmDirect Miro Board UX Diagram](./assets/miro_board_ux.png)

### 📌 Miro Board Overview & Board Structure
Our Miro board maps the complete user journey and technical flow for our focused **FPO-to-Kirana B2B Produce Marketplace**[cite: 1, 2]. It is divided into two core operational frames:

1. **Personas & Core Problem Frame:**
   * **FPO Seller (Rural):** Highlights voice-first Hindi listing needs and Agmarknet Mandi rate visibility to protect farmers from under-pricing[cite: 1].
   * **Kirana Buyer (Local):** Outlines direct bulk produce sourcing needs with instant REST order placement[cite: 1, 2].
   * **Core Metric Tag:** Defines our primary success criteria — *"Enables 1 FPO to supply 50+ local Kirana stores with verified bulk pricing."*[cite: 1]

2. **Low-Fidelity Wireframes & Interaction Flow Frame:**
   * **Screen 1 (FPO Voice Intake):** Low-fidelity mockup showcasing the `Tap & Speak` microphone button, Whisper speech parser preview box, dynamic Agmarknet price bounds, and human-in-the-loop manual override actions[cite: 1].
   * **Screen 2 (Kirana Bulk Order):** Low-fidelity storefront UI showing verified FPO produce cards, live quantity selectors, subtotal calculation, and direct REST order triggers[cite: 1].

---

## 📱 Detailed Step-by-Step User Journeys

### 1. FPO Seller Journey — Voice Intake & Listing Flow
1. **Tap-to-Speak Entry:** The FPO manager opens the listing screen and holds the primary green microphone button (`#00C853`) to speak in native Hindi (e.g., *"कल 200 किलो टमाटर ready हैं"*)[cite: 1].
2. **AI Speech Parsing:** OpenAI Whisper transcribes the speech and extracts structured parameters (`Crop: Tomato`, `Quantity: 200 kg`) in under 1.8 seconds[cite: 1].
3. **Mandi Price Guidance:** The app queries cached Agmarknet market rates and displays a price slider with the fair market range (e.g., **₹22 – ₹26 / kg**)[cite: 1].
4. **Human-in-the-Loop Override:** The FPO lead retains 100% control to adjust or set the final unit price before publishing[cite: 1].
5. **Publishing Listing:** Tapping **"Publish Listing"** broadcasts the available bulk produce to local Kirana buyers[cite: 1].

---

### 2. Kirana Buyer Journey — B2B Marketplace & Order Flow
1. **Browse Local Listings:** The Kirana owner views active produce listings from nearby verified FPOs[cite: 1].
2. **Quantity Selection & Subtotal:** Selects required bulk quantity (e.g., **50 kg**) with real-time subtotal calculation[cite: 1].
3. **Instant B2B Order Placement:** Tapping **"Place Instant Order"** triggers an atomic SQL stock lock and emits an order event via `/api/v1/orders/create`[cite: 1].
4. **Pickup Confirmation:** Displays designated FPO point-pickup window details and collection address[cite: 1].