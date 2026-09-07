🎙️ Multilingual Voice Cataloguer

An AI-powered voice-based catalog creation module designed to help artisans create digital product catalogs without needing to type.

The system allows artisans to describe their products through voice input or uploaded audio in Hindi, Gujarati, or Marathi. The speech is converted into text, translated when required, and transformed into a structured product catalog in Hindi and English.

🌟 Overview

Many artisans have valuable traditional products and stories but face difficulties creating digital catalogs because of:

Limited digital literacy

Difficulty typing product information

Language barriers

Lack of technical knowledge for creating product descriptions

Difficulty preparing standardized product information for online platforms

The Multilingual Voice Cataloguer addresses this problem through a simple voice-first interface.

An artisan can simply speak about their product, and the system processes the input and generates a structured catalog that can be used for digital commerce.

✨ Key Features

🎙️ Voice-Based Catalog Creation

Artisans can describe their product naturally through speech instead of manually typing product details.

📁 Audio File Upload

Users can upload a previously recorded audio file in addition to using live microphone recording.

🌐 Multilingual Input

The system supports three input languages:

🇮🇳 Hindi

🇮🇳 Gujarati

🇮🇳 Marathi

🔄 Automatic Translation

Multilingual speech is processed and translated into the required output language using an AI-based translation pipeline.

🤖 AI-Powered Catalog Generation

The processed product description is converted into structured catalog information using an AI/LLM-based catalog generation module.

🇮🇳 Hindi Catalog

The system can generate the final product catalog in Hindi.

🇬🇧 English Catalog

The system can generate the final product catalog in English, making the information more accessible for digital marketplaces and broader audiences.

📋 Structured Product Information

The generated catalog organizes the artisan's information into useful product fields such as:

Product name

Product description

Category

Materials

Craft details

Traditional information

Other relevant product attributes

🔄 System Workflow

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
                  ┌────────┴────────┐
                  ▼                 ▼
            Hindi Output      English Output

🗣️ Language Support

Input Language

Output Language

Hindi 🇮🇳

Hindi 🇮🇳

Hindi 🇮🇳

English 🇬🇧

Gujarati 🇮🇳

Hindi 🇮🇳

Gujarati 🇮🇳

English 🇬🇧

Marathi 🇮🇳

Hindi 🇮🇳

Marathi 🇮🇳

English 🇬🇧

🧠 AI Pipeline

The module uses a multi-stage AI pipeline:

1. Speech-to-Text

The artisan's voice input is converted into text using Whisper / Faster-Whisper.

Audio → Speech Recognition → Text

2. Translation

If the input language is Gujarati or Marathi, the recognized text can be translated into the required processing language using IndicTrans2.

Gujarati / Marathi → Translation → Hindi / English

3. Catalog Generation

The processed text is passed to the catalog generation component, which extracts relevant product information and produces a structured catalog.

Product Description
        ↓
AI Processing
        ↓
Structured Catalog

🛠️ Technology Stack

Frontend

React

Vite

JavaScript

CSS

Lucide React Icons

Backend

Python

FastAPI

Faster-Whisper

IndicTrans2

AI/LLM-based catalog generation

Testing

Pytest

FastAPI Test Client

📁 Project Structure

multilingual-voice-cataloguer/
│
├── backend/
│   │
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
│   │
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

🚀 Installation & Setup

Prerequisites

Make sure the following are installed:

Python 3.10+

Node.js

npm

Git

⚙️ Backend Setup

Navigate to the backend directory:

cd backend

Create and activate a virtual environment:

Windows

python -m venv venv
venv\Scripts\activate

Install the required dependencies:

pip install -r requirements.txt

Create your environment configuration using the provided example:

.env.example

Then start the FastAPI backend:

python -m uvicorn main:app --reload

The backend will be available at:

http://127.0.0.1:8000

FastAPI Swagger documentation:

http://127.0.0.1:8000/docs

💻 Frontend Setup

Open another terminal and navigate to the frontend:

cd frontend

Install dependencies:

npm install

Start the development server:

npm run dev

The frontend will be available at:

http://127.0.0.1:5173

🎤 User Flow

The module is designed around a simple voice-first experience:

1. Select Input Language
          ↓
2. Speak or Upload Audio
          ↓
3. Process Audio
          ↓
4. Speech Converted to Text
          ↓
5. Translation / Text Processing
          ↓
6. AI Generates Catalog
          ↓
7. View Hindi & English Catalog

This approach minimizes the amount of typing required from the artisan.

🎯 Purpose

The purpose of this module is to make digital catalog creation more accessible to artisans by removing the need for extensive typing and technical knowledge.

Instead of manually entering product information, an artisan can simply speak about their product in Hindi, Gujarati, or Marathi.

The system then processes the speech and generates a structured product catalog in Hindi and English.

This makes the catalog creation process faster, simpler, and more accessible for artisans participating in digital commerce.

🏆 SIH Project Module

This repository contains the Multilingual Voice Cataloguer module developed as part of the larger SIH solution for enabling digital commerce for marginalized artisans.

The module is designed to integrate with the larger artisan marketplace application through its frontend and backend APIs.

👩‍💻 Module Focus

Input:

🎙️ Hindi / Gujarati / Marathi speech
📁 Uploaded audio files

Processing:

🗣️ Speech-to-Text
🔄 Multilingual Translation
🤖 AI-based Catalog Generation

Output:

🇮🇳 Hindi Product Catalog
🇬🇧 English Product Catalog

📌 Future Improvements

Potential future enhancements include:

Support for additional Indian languages

Improved speech recognition for regional accents

Offline/edge speech processing

More customizable catalog fields

Integration with online artisan marketplaces

Voice-based editing of generated catalogs

Improved handling of noisy audio recordings
