# 🎙️ Multilingual Voice Cataloguer

An AI-powered voice-based catalog creation module designed to help artisans create digital product catalogs without needing to type.

The system allows artisans to describe their products through voice input or uploaded audio in **Hindi, Gujarati, or Marathi**. The speech is converted into text, translated when required, and transformed into a structured product catalog in **Hindi and English**.

---

## 🌟 Overview

Many artisans have valuable traditional products and stories but face difficulties creating digital catalogs because of:

- Limited digital literacy
- Difficulty typing product information
- Language barriers
- Lack of technical knowledge for creating product descriptions
- Difficulty preparing standardized product information for online platforms

The **Multilingual Voice Cataloguer** addresses this problem through a simple voice-first interface.

An artisan can simply speak about their product, and the system processes the input and generates a structured catalog that can be used for digital commerce.

---

## ✨ Key Features

### 🎙️ Voice-Based Catalog Creation

Artisans can describe their product naturally through speech instead of manually typing product details.

### 📁 Audio File Upload

Users can upload a previously recorded audio file in addition to using live microphone recording.

### 🌐 Multilingual Input

The system supports three input languages:

- 🇮🇳 Hindi
- 🇮🇳 Gujarati
- 🇮🇳 Marathi

### 🔄 Automatic Translation

Multilingual speech is processed and translated into the required output language using an AI-based translation pipeline.

### 🤖 AI-Powered Catalog Generation

The processed product description is converted into structured catalog information using an AI/LLM-based catalog generation module.

### 🇮🇳 Hindi Catalog

The system can generate the final product catalog in Hindi.

### 🇬🇧 English Catalog

The system can generate the final product catalog in English, making the information more accessible for digital marketplaces and broader audiences.

### 📋 Structured Product Information

The generated catalog organizes the artisan's information into useful product fields such as:

- Product name
- Product description
- Category
- Materials
- Craft details
- Traditional information
- Other relevant product attributes

---

# 🔄 System Workflow

```text
              Voice Input / Audio File
                         │
                         ▼
                 Speech-to-Text
                Whisper / Faster-Whisper
                         │
                         ▼
                   Text Processing
                         │
                         ▼
                Translation Pipeline
                     IndicTrans2
                         │
                         ▼
                 AI Catalog Generator
                         │
                         ▼
             Structured Product Catalog
                         │
                  ┌──────┴──────┐
                  ▼             ▼
            Hindi Output   English Output

```
### 🗣️ Language Support

| Input Language | Output Language |
|---|---|
| Hindi 🇮🇳 | Hindi 🇮🇳 |
| Hindi 🇮🇳 | English 🇬🇧 |
| Gujarati 🇮🇳 | Hindi 🇮🇳 |
| Gujarati 🇮🇳 | English 🇬🇧 |
| Marathi 🇮🇳 | Hindi 🇮🇳 |
| Marathi 🇮🇳 | English 🇬🇧 |


### 🧠 AI Pipeline

The module uses a multi-stage AI pipeline.

```text
1. Speech-to-Text

The artisan's voice input is converted into text using Whisper / Faster-Whisper.

Audio
  ↓
Speech Recognition
  ↓
Text

```
```text
2. Translation

When required, the recognized text is translated using IndicTrans2.

Gujarati / Marathi / Hindi
        ↓
    IndicTrans2
        ↓
Hindi / English
```

### 3. Catalog Generation

```text
The processed text is passed to the catalog generation component, which extracts relevant product information and produces a structured catalog.

Product Description
        ↓
   AI Processing
        ↓
Structured Catalog
```

## 🛠️ Technology Stack

### Frontend

- React
- Vite
- JavaScript
- CSS
- Lucide React Icons

### Backend

- Python
- FastAPI
- Faster-Whisper
- IndicTrans2
- AI/LLM-based catalog generation

### Testing

- Pytest
- FastAPI Test Client

## 📁 Project Structure

```text
multilingual-voice-cataloguer/
│
├── backend/
│   ├── api/
│   │   └── routes/
│   │       └── catalog.py
│   │
│   ├── config/
│   │   └── settings.py
│   │
│   ├── schemas/
│   │   └── catalog.py
│   │
│   ├── services/
│   │   ├── speech_to_text.py
│   │   ├── translation.py
│   │   ├── pipeline.py
│   │   └── catalog_generator.py
│   │
│   ├── utils/
│   │   └── audio.py
│   │
│   ├── tests/
│   │   ├── test_api.py
│   │   ├── test_audio_utils.py
│   │   ├── test_catalog_generator.py
│   │   └── test_translation.py
│   │
│   ├── sample_audio/
│   ├── main.py
│   ├── requirements.txt
│   └── .env.example
│
├── frontend/
│   ├── public/
│   │   └── sample_audio/
│   │
│   ├── src/
│   │   ├── api/
│   │   ├── components/
│   │   │   ├── AudioRecorder.jsx
│   │   │   ├── AudioUploader.jsx
│   │   │   ├── CatalogView.jsx
│   │   │   ├── LanguageSelector.jsx
│   │   │   ├── SampleAudioPicker.jsx
│   │   │   ├── StatusTracker.jsx
│   │   │   └── TextInputDrawer.jsx
│   │   │
│   │   ├── App.jsx
│   │   ├── index.css
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── vite.config.js
│
├── .gitignore
└── README.md
```

## 🚀 Installation & Setup

### Prerequisites

Before running the project, install:

- Python 3.10 or newer
- Node.js and npm
- Git

You also need an internet connection during the initial setup so that Python and frontend dependencies can be downloaded.

---

## ⚙️ Backend Setup

Open a terminal in the project directory.

Navigate to the backend:

```bash
cd backend
```

### 1. Create a Virtual Environment

#### Windows

```bash
python -m venv venv
```

Activate it:

```bash
venv\Scripts\activate
```

After activation, your terminal should show something similar to:

```text
(venv)
```

### 2. Install Python Dependencies

Run:

```bash
pip install -r requirements.txt
```

This installs the required backend libraries, including the speech recognition, translation, API, and testing dependencies.

### 3. Configure Environment Variables

The repository contains:

```text
backend/.env.example
```

Create a new file named:

```text
backend/.env
```

Copy the required configuration from `.env.example` into `.env`.

The `.env` file is intentionally excluded from GitHub using `.gitignore`.

> Do not upload API keys or other private credentials to GitHub.

### 4. Start the Backend

From the backend directory, run:

```bash
python -m uvicorn main:app --reload
```

If the backend starts successfully, it will be available at:

```text
http://127.0.0.1:8000
```

FastAPI API documentation is available at:

```text
http://127.0.0.1:8000/docs
```

Keep this terminal running.

---

## 💻 Frontend Setup

Open a second terminal.

Navigate to the frontend directory:

```bash
cd frontend
```

### 1. Install Frontend Dependencies

Run:

```bash
npm install
```

This installs all required React and frontend dependencies.

### 2. Start the Frontend

Run:

```bash
npm run dev
```

The frontend will normally be available at:

```text
http://127.0.0.1:5173
```

Open that address in a browser.

---

## ▶️ Running the Complete Application

Two terminals should be running simultaneously.

### Terminal 1 — Backend

```bash
cd backend
venv\Scripts\activate
python -m uvicorn main:app --reload
```

### Terminal 2 — Frontend

```bash
cd frontend
npm run dev
```

Then open the frontend in your browser:

```text
http://127.0.0.1:5173
```

The backend API documentation can be accessed through:

```text
http://127.0.0.1:8000/docs
```

---

## 🎤 User Flow

The module follows a simple voice-first workflow:

1. Select Input Language
2. Speak or Upload Audio
3. Process Audio
4. Speech Converted to Text
5. Translation / Text Processing
6. AI Generates Catalog
7. View Hindi & English Catalog

This minimizes the amount of typing required from the artisan.

---

## 🎯 Purpose

The purpose of this module is to make digital catalog creation more accessible to artisans by reducing the need for manual typing and technical knowledge.

Instead of manually entering product information, an artisan can simply speak about their product in Hindi, Gujarati, or Marathi.

The system processes the speech and generates a structured product catalog in Hindi and English.

This makes catalog creation faster, simpler, and more accessible for artisans participating in digital commerce.

---

## 👩‍💻 Module Focus

### Input

- 🎙️ Hindi speech
- 🎙️ Gujarati speech
- 🎙️ Marathi speech
- 📁 Uploaded audio files

### Processing

- 🗣️ Speech-to-Text
- 🔄 Multilingual Translation
- 🤖 AI-based Catalog Generation

### Output

- 🇮🇳 Hindi Product Catalog
- 🇬🇧 English Product Catalog

---

## 📌 Future Improvements

Potential future enhancements include:

- Support for additional Indian languages
- Improved speech recognition for regional accents
- Offline or edge-based speech processing
- More customizable catalog fields
- Integration with online artisan marketplaces
- Voice-based editing of generated catalogs
- Improved handling of noisy audio recordings
- Improved multilingual speech recognition accuracy
Improved handling of noisy audio recordings
Improved multilingual speech recognition accuracy
