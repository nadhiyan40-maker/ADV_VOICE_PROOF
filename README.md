# 🛡️ VoiceProof — Voice-First Evidence Vault for Informal Agreements

> **Turning verbal promises into legally binding, tamper-evident digital proof under Section 63 of India's Bharatiya Sakshya Adhiniyam (BSA), 2023.**

[![License: MIT](https://img.shields.io/badge/License-MIT-teal.svg)](https://opensource.org/licenses/MIT)
[![AI Engine: Whisper-large-v3](https://img.shields.io/badge/AI_Engine-Open--Source_Whisper--large--v3-cyan.svg)](https://github.com/openai/whisper)
[![Legal Compliance](https://img.shields.io/badge/Legal_Compliance-BSA_2023_Sec_63-emerald.svg)](https://www.mha.gov.in)
[![Platform](https://img.shields.io/badge/Platform-Web_Audio_API_%7C_Zero--Install-blue.svg)]()

---

## 📌 The Problem: The Evidence Gap in Informal India

* **90%+ of India’s workforce** is employed in the informal economy (daily-wage laborers, domestic helpers, artisans, street vendors, small shop credit, and personal hand loans).
* Almost all agreements are conducted **purely verbally** over tea or a phone call with zero written paperwork.
* Over **5 crore cases** are pending in Indian courts. When an employer withholds wages or a borrower defaults on a cash loan, victims face zero recourse.
* **The issue is a lack of evidence, not a lack of law.** Existing legal portals assume high literacy, legal jargon, and heavy retainers.

---

## 💡 The Solution: VoiceProof

**VoiceProof** acts as a lightweight, voice-first digital notary. It captures verbal promises in seconds, transcribes and diarizes terms using **open-source AI (`whisper-large-v3`)**, measures the physical vocal cords of both parties using **acoustic voice biometrics (32-band FFT)** to prevent impersonation fraud, and seals the agreement with a **SHA-256 cryptographic hash** into an enforceable **Section 63 BSA 2023 Court Evidence PDF**.

---

## ✨ Key Features

### 1. 🎙️ Open-Source Multilingual Speech AI
* Powered by the state-of-the-art **`whisper-large-v3`** model (Open-source, MIT License).
* Seamlessly transcribes and structures informal speech across **English, Hindi/Hinglish, and Tamil**.
* High-speed, zero-install cloud inference via Groq LPUs for sub-second response times.

### 2. 🧬 Acoustic Voice Biometrics & Anti-Spoof Engine
* **Physical Vocal Tract Analysis**: Uses browser-native Web Audio API to run a live **32-Band Fast Fourier Transform (FFT)** and **Fundamental Pitch ($F_0$) Autocorrelation**.
* **Anti-Impersonation Math**: Computes genuine **Cosine Similarity** between Speaker 1 and Speaker 2.
* **Spoof Protection**: If a single person attempts to fake both the Lender and Borrower roles, the engine detects identical vocal tract geometry and locks the vault.

### 3. 🔗 Two-Party Split Links & Live Remote Ratification
* **Lender Portal (`?role=lender`)**: The lender records the offer and locks the extracted terms (Amount, Due Date, Jurisdiction).
* **Borrower Portal (`?role=borrower`)**: Generates a shareable URL that loads an incoming offer screen for the borrower on their own device.
* **Live Cross-Device Sync**: Powered by browser `BroadcastChannel` API—when the borrower clicks "Accept" in Tab 2, Tab 1 on the lender's screen automatically turns green in real time!

### 4. 🛑 Automated Verbal Dissent Gatekeeper
* Listens for spoken rejection phrases (*"I reject"*, *"Disagree"*, *"Cannot accept"*, *"Mana"*).
* If the borrower verbally objects, the contract is automatically voided, preventing unilateral or coerced contracts.

### 5. ⚖️ Dispute-Ready BSA 2023 Certified Evidence PDF
* Produces an automated, court-admissible certificate formatted specifically to meet **Section 63 of Bharatiya Sakshya Adhiniyam, 2023** (formerly Section 65B of the Indian Evidence Act, 1872).
* Contains verbatim diarized quotes, physical acoustic frequency proofs (Hz), dual-party ratification timestamps, and an immutable SHA-256 cryptographic seal.

---

## 🏗️ Technical Architecture
[ Oral Exchange / Spoken Promise ]
                                   │
              ┌────────────────────┴────────────────────┐
              ▼                                         ▼
     [ Lender Audio Stream ]                 [ Borrower Audio Stream ]
              │                                         │
              ├────────────────────┬────────────────────┤
              ▼                                         ▼
  [ 32-Band FFT & F₀ Pitch ]               [ Whisper-large-v3 API ]
 (Acoustic Voiceprint Vector)             (Open-Source Speech Core)
              │                                         │
              ▼                                         ▼
  [ Cosine Similarity Audit ]              [ Dynamic Entity Extractor ]


  ---

## 💻 Tech Stack

* **Frontend**: HTML5, Tailwind CSS, Phosphor Icons
* **Acoustic Biometrics**: Web Audio API (`AudioContext`, `AnalyserNode`, 1024-point FFT, Time-Domain Autocorrelation)
* **AI Engine**: OpenAI's `whisper-large-v3` (Open-Source, MIT License) hosted via Groq Cloud Inference
* **Cryptography**: `CryptoJS` (SHA-256 Hash Chaining)
* **Document Engine**: `jsPDF` (Automated Section 63 Court Certificate Generator)
* **State Synchronization**: Browser `BroadcastChannel` & Base64 URI State Payloads

---

## 🚀 Quick Start Guide (Zero Installation)

You do **not** need to install Python, terminal packages, or heavy dependencies. The entire app runs directly in any modern browser (Chrome, Edge, Brave).

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/VoiceProof.git
cd VoiceProof
