Multilingual Voice Cataloguer

An AI-powered voice-first catalog creation module designed for artisans and micro-entrepreneurs who may find typing difficult or inconvenient.

The application lets an artisan speak or upload an audio file describing a product in Hindi, Gujarati, or Marathi. The system converts the speech into text, translates it when required, and generates a structured product catalog in Hindi and English.

🌟 Overview

Creating a digital product catalog can be difficult for artisans because it may require:

Typing product information

Writing product descriptions

Knowing English

Structuring information into catalog fields

Using technical e-commerce tools

This module provides a simple voice-first interface so an artisan can describe a product naturally.

Basic Flow

Voice / Audio → Speech-to-Text → Translation → AI Catalog Generation → Hindi + English Catalog

✨ Key Features

🎙️ Voice-First Catalog Creation

The artisan can describe their product using their voice instead of typing.

📁 Audio File Upload

The application supports uploading a recorded audio file in addition to live microphone input.

🌐 Multilingual Input

The system accepts speech in:

🇮🇳 Hindi

🇮🇳 Gujarati

🇮🇳 Marathi

📝 Bilingual Output

Generated catalog information is available in:

🇮🇳 Hindi

🇬🇧 English

🤖 AI-Based Catalog Generation

The system converts an unstructured spoken description into structured product information such as:

Product name

Product description

Category

Materials

Price

Dimensions

Craft details

Other relevant product attributes

🔄 Translation Support

If the spoken language differs from the desired catalog language, the system can translate the content before generating the final catalog.

🎨 Simple Artisan-Friendly Interface

The frontend focuses on a clean and accessible workflow with minimal typing and a straightforward voice/upload interaction.

🔄 Workflow

             ┌──────────────────────┐
             │   Artisan speaks     │
             │   or uploads audio   │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │   Speech-to-Text     │
             │  Faster-Whisper      │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │     Translation      │
             │     IndicTrans2      │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │   AI Catalog         │
             │     Generation       │
             └──────────┬───────────┘
                        │
                        ▼
          ┌──────────────────────────────┐
          │   Structured Product Catalog │
          │       Hindi + English        │
          └──────────────────────────────┘

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

The module combines speech recognition, translation, and structured AI generation.

1. Speech-to-Text

Faster-Whisper is used to convert spoken audio into text.

It supports the application's multilingual voice input workflow.

2. Translation

IndicTrans2 is used when translation is required between the supported Indian languages and English.

3. Catalog Generation

The processed text is sent to the AI catalog-generation layer, which extracts important product information and organizes it into structured fields.

4. Final Output

The generated information is presented as a clean product catalog in Hindi and English.

🛠️ Tech Stack

Frontend

React

Vite

JavaScript

CSS

Backend

Python

FastAPI

Uvicorn

AI / ML

Faster-Whisper

IndicTrans2

LLM-based structured catalog generation

Development

Git

GitHub

REST API

Swagger / OpenAPI

📁 Project Structure

multilingual-voice-cataloguer/
│
├── backend/
│   ├── main.py
│   ├── requirements.txt
│   ├── .env.example
│   └── ...
│
├── frontend/
│   ├── src/
│   ├── package.json
│   └── ...
│
├── temp_audio/
│   └── ...
│
├── .gitignore
└── README.md

temp_audio/, environment files, caches, and other local/generated files should not be committed to Git.

🚀 Getting Started

Follow these steps to run the project locally.

1. Clone the Repository

git clone https://github.com/Anushka-ctrl365/multilingual-voice-cataloguer.git
cd multilingual-voice-cataloguer

2. Backend Setup

Open a terminal in the project root.

Create and activate a Python virtual environment:

Windows

python -m venv venv
venv\Scripts\activate

macOS / Linux

python3 -m venv venv
source venv/bin/activate

Install the backend dependencies:

cd backend
pip install -r requirements.txt

3. Configure Environment Variables

Inside the backend folder, create a file named:

.env

Use .env.example as the reference for the required environment variables.

Example:

# Add the required API/model configuration here.
# Do not commit your real API keys to GitHub.

Keep API keys and other secrets private.

4. Start the Backend

From the backend directory:

python -m uvicorn main:app --reload

The backend will normally be available at:

http://127.0.0.1:8000

Swagger API Documentation

Open:

http://127.0.0.1:8000/docs

This provides an interactive interface for testing the backend APIs.

5. Start the Frontend

Open a new terminal.

Go to the frontend directory from the project root:

cd frontend

Install frontend dependencies:

npm install

Start the development server:

npm run dev

The terminal will display the local frontend URL, normally similar to:

http://localhost:5173

Open that address in your browser.

🎤 How to Use the Application

Step 1 — Select a Language

Choose the language in which the artisan will describe the product:

Hindi

Gujarati

Marathi

Step 2 — Provide the Product Description

The artisan can either:

🎙️ Record speech using the microphone, or

📁 Upload an existing audio file.

Step 3 — Process the Audio

The system transcribes the audio and processes the resulting text.

Step 4 — Generate the Catalog

The AI extracts the relevant product information and creates a structured catalog.

Step 5 — View the Result

The final product information is displayed in Hindi and English.

🎯 Purpose of the Module

This module focuses specifically on reducing the technical and language barriers involved in digital catalog creation.

Instead of requiring artisans to type and manually prepare product information, they can simply speak about their product in their preferred supported language.

The system then transforms that natural speech into structured, bilingual catalog content suitable for digital commerce.

🏆 SIH Project Module

This repository contains the multilingual voice and AI cataloging module of the larger Smart India Hackathon solution.

The broader solution is intended to help marginalized artisans gain better access to digital markets and year-round commerce.

This repository specifically focuses on:

Voice-based product information collection

Multilingual speech recognition

Translation

AI-powered catalog generation

Hindi and English catalog output

Other modules of the larger solution, such as image enhancement and dynamic pricing, are outside the scope of this repository.

🔮 Future Improvements

Possible future enhancements include:

More regional Indian languages

Better handling of regional accents and dialects

Offline or low-connectivity support

Improved speech recognition for noisy environments

Product image integration

Automatic catalog export

Direct e-commerce marketplace integration

QR-based product storytelling

🔐 Security Notes

Never commit API keys or passwords.

Keep .env files out of version control.

Do not upload sensitive personal information.

Validate uploaded audio files before processing.

Apply appropriate authentication and authorization when deploying the application publicly.

📌 Repository

GitHub:
https://github.com/Anushka-ctrl365/multilingual-voice-cataloguer

👩‍💻 Module Focus

Multilingual Voice Input + AI Catalog Generation

Input: Hindi, Gujarati, Marathi
Output: Hindi, English

Built as part of a Smart India Hackathon project focused on empowering marginalized artisans through accessible digital tools.
