<div align="center">

# AgriTrust AI

### Storage that responds to the produce inside it

IoT sensor pods, a stimulus engine and an AI perishability model that protect fresh produce before it spoils, with voice-first input for farmers.

[![IoT](https://img.shields.io/badge/IoT-sensor%20pods-2e7d32)](#how-it-works)
[![Voice input](https://img.shields.io/badge/voice-10%20Indian%20languages-c62828)](#voice-first-for-farmers)
[![Web Speech API](https://img.shields.io/badge/Web%20Speech-API-4285F4)](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API)
[![Browser demo](https://img.shields.io/badge/demo-HTML%20%2B%20JS-F7DF1E?logo=javascript&logoColor=black)](#try-the-browser-demo)

**By Team Stack Underflow**

![AgriTrust AI Storage Pod 4B dashboard](docs/screenshots/dashboard.png)

</div>

---

## About

Fresh produce is often lost before anyone can act:

- **Up to 30–40% spoils** in storage and transit.
- **Cold storage tracks air temperature, not decay.** Temperature logs can look normal while a crop is already losing shelf life.
- **Farmers lack price visibility** and are pushed into distress sales.

Produce is alive, but storage treats it as static. It keeps **breathing** (respiration continues after harvest), it **ripens** (ethylene affects nearby crops), its records are **manual** (audits are slow and easy to fake), and it **loses value** before decay is visible.

**AgriTrust AI turns storage into a responsive hub** that senses how the produce is doing, predicts its shelf life and acts before the value is gone.

## How it works

Four connected layers move from sensing to protection:

| Layer | What it does |
|---|---|
| **1. IoT sensor pods** | Read the environment around each batch |
| **2. Stimulus engine** | Interpret how the produce is responding |
| **3. AI perishability model** | Estimate changing risk by crop and batch |
| **4. Automated actions** | Protect value before the window closes |

### Four signals

| Signal | Why it matters | Safe range in the demo |
|---|---|---|
| **Ethylene** | Ripening gas that speeds up nearby crops | 0–1 ppm |
| **Temperature** | Heat speeds up respiration and decay | 2–8 °C |
| **Humidity** | Humidity plus heat means mould risk | 65–85% RH |
| **CO₂** | Rising levels signal respiration and poor ventilation | 400–1000 ppm |

### Combinations, not single values

The engine reads the signals together rather than waiting for one number to cross a line. High ethylene at a normal temperature can still mean premature ripening. The **estimated remaining shelf life (ERSL)** is recalculated for every crop and every batch. For example, Batch #402 of Jyoti potatoes can drop from 12 days to 3.

### When risk rises, the system acts

- **Protect the room:** ventilation and ethylene scrubbers switch on automatically.
- **Protect the sale:** batches with under 3 days left are listed at a 20–40% discount for B2B buyers.
- **Protect compatibility:** crops like apples and leafy greens are flagged before they share a room.
- **Protect dry goods:** dry grains stored beside humid produce are flagged too.

### Voice-first for farmers

Farmers can add produce by speaking in **Hindi, Bengali, Tamil, Telugu, Marathi, Gujarati, Kannada, Malayalam, Punjabi or English**. The app extracts the crop, weight and readiness from what they say, so there's less typing and onboarding is faster.

### One trusted record per batch

Every batch has an **origin passport**: a hash-chained log of its journey from farm to buyer, including listing, storage problems and discount sales. Farmers see condition and price signals before selling, buyers see what is available with context, and audits become automatic instead of paperwork.

## Try the browser demo

`index.html` is a self-contained demo of **Storage Pod 4B**, a cold room in West Bengal with a simulated live sensor feed. Open it in any modern browser, or publish it with GitHub Pages.

| Panel | What you can do |
|---|---|
| **Live sensor readings** | Watch ethylene, temperature, humidity and CO₂ against their safe ranges. Press **Spike ethylene** or **Spike humidity + heat** to cause a problem, and **Reset pod** to start again |
| **Shelf-life countdown** | See days left for each batch (Fresh, Ripening, Dispatch now) and automatic distress-sale listings |
| **Add produce by voice** | Pick a language, tap **Speak** (or type), and add a batch to the inventory |
| **Batch origin passport** | Follow a batch's history and check that the record hasn't been changed |
| **Alerts and events** | A log of sensor breaches and automatic actions |
| **Storage compatibility check** | Check whether two of 40 vegetables, fruits, grains and pulses can share a room |

| Add produce by voice | Compatibility check |
|---|---|
| ![Voice listing](docs/screenshots/voice-listing.png) | ![Compatibility check](docs/screenshots/compatibility.png) |

In the demo:

- **Sensor readings are simulated**, and a simple stress formula stands in for the AI perishability model.
- **Voice input uses the browser's Web Speech API**, which works best in Chrome or Edge and needs microphone permission. You can also type. An example sentence is filled in for each language.
- **Prices are sample values**, not live market prices.
- **The origin passport uses a simple in-browser hash chain** to show how tampering is detected. It isn't a blockchain or a production-grade signature.
- **Compatibility results use typical values** for ethylene and humidity. Check crop-specific guidance before storing.

## Project structure

```
agritrust-ai/
├── index.html                          # Self-contained Storage Pod 4B demo
└── docs/
    ├── AgriTrust-AI.pptx               # Pitch deck
    ├── AgriTrust-Storage-Pod-4B.pdf    # Printout of the dashboard
    └── screenshots/
```

## Roadmap

- [ ] Real IoT sensor pods for ethylene, temperature, humidity and CO₂
- [ ] Perishability model trained on real storage data
- [ ] Connection to ventilation and scrubber controls
- [ ] Live market prices and a B2B buyer marketplace
- [ ] Tamper-proof batch records for auditors

## Team

Built by **Team Stack Underflow**. Presented by **Rishi Chowdhury**.

## License

Released under the [MIT License](LICENSE).
