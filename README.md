🐍 SnakesLucifer AI Chat

An advanced full-stack AI chat application built with the MERN stack and Google Gemini API — featuring streaming responses, session context, and a beautiful glassmorphic dark UI.

🧠 Overview

SnakesLucifer is an AI-powered chatbot built using:

🧩 MERN Stack (MongoDB, Express, React, Node.js)

🪄 Gemini API (Google Generative AI)

⚡ Server-Sent Events (SSE) for real-time streaming responses

🧊 Glassmorphic dark theme with light/dark mode toggle

💾 MongoDB persistence for messages and sessions

📁 Project Structure
SnakesLucifer/
├── nimbus-chat-backend/         # Express + Gemini backend
│   ├── server.js                # Main server entry
│   ├── routes/
│   │   └── chat.js              # Chat API routes
│   ├── services/
│   │   └── geminiService.js     # Handles Gemini API requests
│   ├── models/
│   │   ├── Message.js           # Message schema
│   │   ├── Session.js           # Session schema (optional)
│   │   └── User.js              # User schema (optional)
│   ├── middleware/
│   │   ├── auth.js              # JWT auth (optional)
│   │   ├── rateLimiter.js       # Rate limiting
│   │   └── safetyCheck.js       # Input guardrails
│   └── .env                     # Environment variables
│
└── nimbus-chat-frontend/        # React frontend
    ├── src/
    │   ├── components/
    │   │   ├── ChatWindow.jsx
    │   │   ├── MessageBubble.jsx
    │   │   └── ProviderSelector.jsx
    │   ├── api/
    │   │   └── chatApi.js
    │   ├── App.jsx
    │   ├── index.js
    │   └── styles.css
    ├── package.json
    └── .env

⚙️ Backend Setup (Node + Express)
1️⃣ Install dependencies
cd nimbus-chat-backend
npm install

2️⃣ Configure .env

Create a .env file in the backend root with the following:

PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.xxxxxx.mongodb.net/snakeslucifer
GEMINI_API_KEY=YOUR_GOOGLE_GEMINI_API_KEY
GEMINI_MODEL=gemini-2.5-flash


🧩 You can get your Gemini API key from https://aistudio.google.com/app/apikey

3️⃣ Run the backend
npm start


If successful, you’ll see:

✅ MongoDB connected successfully
🚀 Server running on port 5000

💻 Frontend Setup (React)
1️⃣ Install dependencies
cd nimbus-chat-frontend
npm install

2️⃣ Configure environment (optional)

In nimbus-chat-frontend/.env:

REACT_APP_API_URL=http://localhost:5000

3️⃣ Run the frontend
npm start


Your app will launch at http://localhost:3000
.

💬 Usage

Open http://localhost:3000

Type a message and hit Send

Watch the Gemini model stream responses in real-time

Toggle between dark/light mode with the 🌙 / ☀️ button

Clear chat with 🧹

All messages are stored in MongoDB

🔥 Key Features
Feature	Description
💎 Gemini Integration	Uses Google Gemini API for AI chat
🔁 SSE Streaming	Real-time response streaming via Server-Sent Events
💾 MongoDB Persistence	Saves messages and sessions
🧊 Dark/Light Theme	Switch seamlessly between modes
🛡️ Rate Limiting & Safety	Basic content and input validation
🧱 Modular Code	Service-based backend with clean structure
🧠 Context Retention	Preserves per-session history
🧰 Developer Ready	Easy to extend for other providers (OpenAI, Dialogflow)
🧠 Tech Stack
Layer	Technology
Frontend	React (Vite or CRA), Tailwind CSS (optional)
Backend	Node.js, Express
AI Provider	Google Gemini API
Database	MongoDB Atlas
Realtime	Server-Sent Events (SSE)
Auth	JWT (optional)
🧱 Example Backend Endpoints
POST /api/chat

Sends a message and receives a streaming AI response.

curl -X POST http://localhost:5000/api/chat \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello Gemini!"}'


Response (streamed):

data: {"text": "Hello from Gemini..."}
data: [DONE]

🛠️ Development Commands
Command	Description
npm start	Start dev server
npm run dev	Frontend dev mode
npm run build	Build production frontend
npm test	Run tests
🧑‍💻 Environment Variables
Variable	Description
PORT	Backend server port
MONGO_URI	MongoDB connection string
GEMINI_API_KEY	Google AI Studio key
GEMINI_MODEL	Gemini model name (e.g., gemini-2.5-flash)
🧰 Troubleshooting
❌ connect ECONNREFUSED 127.0.0.1:27017

MongoDB not running locally
Fix: Use MongoDB Atlas or start local MongoDB manually.

❌ API_KEY_INVALID

Invalid Gemini API key
Fix: Generate a new key from AI Studio
 and replace it in .env.

❌ Stream Interrupted

Usually a frontend fetch or CORS issue
Fix: Ensure the backend’s /api/chat route uses proper CORS headers and SSE handling.

🌌 UI Highlights

Fullscreen glassmorphic design

Animated message bubbles

Responsive for all devices

Smooth background gradients

Cinematic dark theme with neon accents

⚖️ License

This project is open-source under the MIT License.

🐍 Author

SnakesLucifer AI
🧠 Developed by [Your Name / Team]
💬 Powered by Google Gemini API
🌐 Inspired by ChatGPT & Gemini Web
