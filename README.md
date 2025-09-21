# Byte AI Prototype - Google Cloud Gen AI Hackathon

![Byte AI Logo](https://via.placeholder.com/150?text=Byte+AI) <!-- Replace with actual logo URL or path -->

[![Python](https://img.shields.io/badge/Python-3.12-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![GitHub Issues](https://img.shields.io/github/issues/ajmal-uk/Byte-Ai-Prototype---Google.svg)](https://github.com/ajmal-uk/Byte-Ai-Prototype---Google/issues)
[![GitHub Stars](https://img.shields.io/github/stars/ajmal-uk/Byte-Ai-Prototype---Google.svg)](https://github.com/ajmal-uk/Byte-Ai-Prototype---Google/stargazers)

## Overview

Byte AI is an advanced, privacy-focused AI chat assistant developed as a prototype for the Google Cloud Gen AI Exchange Hackathon 2025. Built using Google Cloud’s Generative AI tools (primarily the Gemini API), it serves as a versatile productivity tool for coding assistance, content writing, real-time web searches, and image generation/modification. The app emphasizes user-friendly interactions without requiring sign-ups, with features like context-aware responses, theme customization, and secure data handling.

This project demonstrates how Google Cloud’s AI can empower India’s digital ecosystem by providing an accessible, free alternative to proprietary chatbots like ChatGPT. It integrates multi-modal AI capabilities in a web application, focusing on privacy, efficiency, and scalability.

**Live Demo**: [Byte AI on PythonAnywhere](https://byteai.pythonanywhere.com)  
**Demo Video (3-min Explanation)**: [Watch on Google Drive](https://drive.google.com/file/d/1aOPEcTOLcquEiOUWNAObFT7BhbuYEGv2/view?usp=sharing)

## Key Features

- **Core Chat Functionality**: Context-aware AI responses using Gemini AI models; supports math (LaTeX rendering), code (syntax highlighting and preview), and markdown parsing.
- **Web Search Integration**: Real-time Google searches with India-specific localization (e.g., currency conversions); intelligently skips for non-factual queries.
- **Deep Thinking Mode**: Step-by-step reasoning for complex queries, visualized with animated progress indicators.
- **Image Generation & Editing**: Prompt-based image creation and modification via Gemini AI; includes auto-watermarking with 'BYTE', download, and edit options.
- **User Profile & Customization**: Editable name, DOB, and avatar; supports 6+ themes (light, dark, system, aurora night, midnight tech, warm dusk); session history management.
- **Advanced Tools**: HTML code preview in iframes, like/dislike feedback, copy/download for code/images, toast notifications for actions.
- **Privacy & Security Features**: No server-side data storage; uses IndexedDB for local images/profiles and LocalStorage for sessions/themes; options to clear data/cache.
- **UI/UX Enhancements**: Auto-scrolling chat, touch-optimized for mobile, loading animations, welcome screen for new users, and responsive design.

## How It Works

1. **User Input**: Enter a prompt in the chat interface (e.g., "Generate an image of a futuristic city" or "Debug this Python code").
2. **Intent Analysis**: The system detects intents (text, search, think, image) using NLP.
3. **API Routing**: Calls Gemini AI for processing; integrates Google Search for real-time info.
4. **Response Generation**: Parses and renders output (text with typing effect, images with loading animation).
5. **Interaction**: Users can copy, edit, like/dislike, or download responses.
6. **Storage**: Sessions saved locally for persistence across reloads.

For a visual overview, see the [Process Flow Diagram](#architecture) below.

## Differentiation from Existing Solutions

- **Vs. ChatGPT/Gemini Web**: Free unlimited access, no subscriptions; superior privacy with local-only data.
- **Privacy-First**: End-to-end anonymous; no harvesting, complies with India's DPDP Act.
- **Hybrid & Integrated**: Combines text/image/search/think in one app; mobile-optimized UI.
- **India-Optimized**: Localized searches, low-bandwidth support for rural users.
- **Open & Customizable**: Flask-based with open libraries; easy to extend.

## Problem Solved

Byte AI addresses the lack of affordable, secure AI tools for Indian students/developers:
- **Productivity Gains**: 40-50% faster workflows for coding/writing/images.
- **Accessibility**: Free, no-login, offline-capable elements.
- **Privacy**: Local storage prevents leaks.
- **Scalability**: Gemini AI handles high loads via Google Cloud.

## Unique Selling Points (USPs)

- **Free & Accessible**: No costs or sign-ups.
- **Gemini-Powered**: High-performance multi-modal AI.
- **Customizable**: Themes, profiles, and India-localized features.
- **Secure**: Privacy-focused with efficient design (<2s responses).

## Technologies Used

- **Backend**: Python 3.12, Flask, CORS.
- **Frontend**: HTML5, CSS3 (variable-based themes), JavaScript (ES6+).
- **Libraries**: Marked.js (markdown), Highlight.js (code syntax), KaTeX (math), Compromise (NLP).
- **AI/ML**: Google Generative AI (Gemini for text/images/search).
- **Storage**: IndexedDB (images/profiles), LocalStorage (sessions/themes).
- **Tools**: PlantUML (diagrams), Boxicons/Bootstrap Icons (UI), Google Fonts.
- **Deployment**: PythonAnywhere; scalable to Google Cloud Run.

## Architecture Diagram

High-Level Flow:
- Frontend (Browser) → Flask Server → Gemini AI/Google Search → Local Storage → Render Response.

PlantUML Representation (Render via [PlantUML Online](https://www.plantuml.com/plantuml)):
```
@startuml
skinparam componentStyle rectangle
[User Interface\n(HTML/JS/CSS)] as UI
[Flask Server] as Flask
[Gemini AI\n(Google Cloud)] as Gemini
[Google Search] as Search
[IndexedDB/LocalStorage] as Storage

UI -> Flask : HTTP Request (Prompt)
Flask -> Gemini : API Call (Text/Image Gen)
Flask -> Search : Web Search Query
Flask <-> Storage : Save/Retrieve (Images/Sessions)
Flask -> UI : JSON Response
@enduml
```

Generated Diagram Prompt (for tools like DALL-E): "System architecture diagram for Byte AI: UI → Flask → Gemini AI/Google Search → Storage. Use icons, blue connections."

## Installation & Setup

1. **Prerequisites**:
   - Python 3.12+
   - Google Cloud API keys (Gemini) – Set in `GEMINI_API_LIST` in `app.py`.
   - Install dependencies: `pip install -r requirements.txt` (includes Flask, google-generativeai, googlesearch-python, etc.).

2. **Clone Repo**:
   ```
   git clone https://github.com/ajmal-uk/Byte-Ai-Prototype---Google.git
   cd Byte-Ai-Prototype---Google
   ```

3. **Setup Environment**:
   - Create `.env` and add your Gemini API keys.
   - Run: `python app.py` (starts on http://127.0.0.1:8080).

4. **Deployment**:
   - Host on PythonAnywhere or Google Cloud Run.
   - Ensure API keys are securely managed.

## Usage

- Visit the app URL.
- Enter name on welcome screen (stored locally).
- Type prompts: e.g., "/image A futuristic AI city" for image gen.
- Toggle options: Search (globe), Think (atom), Image (image icon).
- Interact: Copy/edit/like responses; manage sessions in sidebar.

Demo Video: [Watch Here](https://drive.google.com/file/d/1aOPEcTOLcquEiOUWNAObFT7BhbuYEGv2/view?usp=sharing)


## Team & Credits

- **Team Lead**: MUHAMMED AJMAL U K (MCA at CET, Thiruvananthapuram)  
- **Members**: Abhinav Raj P (MCA at CET), Amarjith Anandh (MCA at CET), Gokul Pavithran (MCA at CET Thalassery)  

Built for Google Cloud Gen AI Hackathon 2025. Thanks to Google Cloud for Gemini API!

For issues, contact: ajmaluk.me@gmail.com
