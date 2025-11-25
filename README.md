# 📧 Gmail AI Reply Assistant

### *AI-powered Chrome Extension for Smart Email Replies (Spring Boot + Gemini)*

A Chrome Extension that generates intelligent Gmail replies using
**Google Gemini AI**, powered by a secure **Spring Boot backend**.\
This tool reads Gmail threads, sends them to your backend, receives the
AI-generated content, and inserts it automatically into the Gmail
compose box.

## 🚀 Features

### 🔹 Chrome Extension

-   "Generate Reply" button inside Gmail
-   Reads current email thread from Gmail DOM
-   Auto-inserts generated reply into the compose box
-   Clean popup UI for manual triggering

### 🔹 Spring Boot Backend

-   REST API to generate replies via Gemini
-   API key stored securely on backend (never in extension)
-   Input sanitization + model formatting
-   Configurable model and API URL

### 🔹 AI Capabilities

-   Generates polite, context-aware replies
-   Understands tone and email history
-   Can rewrite drafts or generate fresh replies

## 🏗️ Architecture

    Chrome Extension → Spring Boot API → Gemini API
           │                 │
           └─ Insert reply into Gmail compose box

## 📦 Project Structure

    root/
    │
    ├── chrome-extension/
    │   ├── manifest.json
    │   ├── content.js
    │   ├── content.css
    │   
    └── spring-boot-backend/
        ├── src/main/java/...
        ├── src/main/resources/application.properties
        └── pom.xml

## 🔧 Setup Instructions

### ✔️ 1. Clone the Repository

``` sh
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

## ⚙️ 2. Configure Spring Boot Backend

Open:

    spring-boot-backend/src/main/resources/application.properties

Add:

    gemini.api.url=https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent
    gemini.api.key=YOUR_API_KEY
    server.port=8080

Run backend:

``` sh
mvn spring-boot:run
```

Backend available at:

    http://localhost:8080

## 🔌 3. Load Chrome Extension

1.  Open **chrome://extensions/**
2.  Enable **Developer Mode**
3.  Click **Load Unpacked**
4.  Select the `chrome-extension/` folder

Extension is now installed 🎉

## 🧪 Usage

1.  Open **Gmail**
2.  Open any email thread
3.  Use:
    -   Extension popup\
    -   OR injected "Generate Reply" button (if implemented)
4.  AI reply is inserted automatically in Gmail's compose box

## 🔐 Security

-   API key stored **only** on backend\
-   No email content stored anywhere\
-   Only your backend endpoint is allowed by CORS\
-   Extension uses HTTPS fetch for communication

## 🧱 Technologies Used

### Frontend (Chrome Extension)

-   JavaScript (Vanilla)
-   Manifest V3
-   Chrome Scripting API
-   DOM extraction

### Backend (Spring Boot)

-   Spring Boot 3
-   WebClient
-   REST API
-   Java 17+

### AI

-   Google Gemini 1.5 Flash/Pro

## 🛠️ Future Roadmap

-   Tone selector (Formal, Friendly, Brief)
-   Email summarization
-   Outlook Web support
-   Auto-detect intent for reply
-   UI themes for extension popup

## 🤝 Contributing

Pull requests and feature suggestions are welcome!

## 📜 License

MIT License

## ⭐ Support

If you found this project useful, please give it a **star ⭐ on
GitHub**!
