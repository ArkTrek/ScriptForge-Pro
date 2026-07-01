# ScriptForge Pro 🎬

![Python Version](https://img.shields.io/badge/python-3.10-blue.svg)
![Flask](https://img.shields.io/badge/Flask-Web%20Framework-lightgrey.svg)
![Gemini](https://img.shields.io/badge/Google-GenAI-orange.svg)
![Firebase](https://img.shields.io/badge/Firebase-RTDB-yellow.svg)

**ScriptForge Pro** is a fully functional, production-grade web application designed to automate the pre-production writing process. Powered by Google's Gemini 2.5 Flash model, this tool generates cinema-grade scripts, fast-paced reel concepts, and trending content ideas, automatically formatting and compiling them into professional PDF documents.

## ✨ Features

* **Cinematic Scripting Engine:** Generates highly detailed, formatted scene headings, action descriptions, and culturally nuanced dialogues.
* **Multi-Mode Output:** * *Cinema Scripts:* Long-form, narrative-driven storytelling.
    * *Reel/Shorts:* Timed 30s/60s scripts with structured hooks and CTAs.
    * *Trending Feed:* Viral video ideation and quick-hit concepts.
* [cite_start]**Automated PDF Compilation:** Scripts are generated in Markdown and instantly converted to styled Pdfs. 
* **Secure Studio Access:** Protected via Firebase Realtime Database (RTDB) authentication.
* **Activity Logging:** Background worker threads log all user prompts and generation requests silently.

## 📂 Project Structure

All outputs are kept strictly organized on the server:

```text
├── app.py                   # Main application and AI routing logic
[cite_start]├── requirements.txt         # Pip dependencies
├── generated_assets/
│   ├── logs/                # System activity and prompt logs
│   └── pdfs/                # Ready-to-download, formatted PDF scripts
└── templates/               # (Inline within app.py) Dashboard and UI

```

## 🚀 Getting Started

### Prerequisites

* Python 3.10+
* Google Gemini API Key
* Firebase Project (with Realtime Database enabled)

### 1. Installation

Clone the repository and install the required dependencies:

```bash
git clone [https://github.com/arktrek/ScriptForge-Pro.git](https://github.com/arktrek/ScriptForge-Pro.git)
cd ScriptForge-Pro
pip install -r requirements.txt

```

(Note: The environment relies on standard data science and web tools including `flask`, `firebase-admin`, `google-genai`, `markdown`, and `xhtml2pdf`.)

### 2. Environment Variables

Create a `.env` file in the root directory and populate it with your credentials:

```env
GOOGLE_API_KEY="your_gemini_api_key_here"
FLASK_SECRET_KEY="your_secure_flask_session_key"
FIREBASE_DB_URL="[https://your-project-id.firebaseio.com/](https://your-project-id.firebaseio.com/)"
FIREBASE_KEY_PATH="keys.json"

```

### 3. Firebase RTDB Setup

To use the login portal, you must configure your Firebase Realtime Database to store user credentials. Ensure your database contains the following structure:

```json
{
  "MainKeys": {
    "Adm": {
      "your_username": "your_secure_password"
    }
  }
}

```

*Place your Firebase Admin SDK service account file in the root directory and name it `keys.json` (or match your `.env` configuration).*

### 4. Run the Studio

Start the application:

```bash
python app.py

```

Access the studio at `http://localhost:5000`. Login using the credentials set in your Firebase RTDB, select your output mode, and generate production-ready assets. All completed scripts will be saved directly to the `generated_assets\pdfs` directory.

## 👨‍💻 Author

**Arpit Ramesan** * GitHub: [@arktrek](https://github.com/arktrek)
