# AgriAssist - AI-Powered Smart Farming Platform

AgriAssist is a comprehensive web application designed to empower Indian farmers with cutting-edge AI technology. It provides real-time crop disease analysis, personalized farming advice, and market insights using advanced LLMs (Llama 3.3 & Llama 3.2 Vision) via the Groq API.

## 🚀 Key Features

*   **AI Crop Disease Scanner**: Instantly analyze crop photos to detect diseases, severity, and get treatment recommendations (Powered by Llama 3.2 Vision).
*   **AI Assistant (Copilot)**: A conversational assistant for farming queries, supporting multiple languages (Hindi, Telugu, English) and context-aware advice.
*   **Secure Authentication**: User registration and login system for personalized history.
*   **Market & Analytics**: Tools for tracking market prices and farm analytics (in development).
*   **Weather Integration**: Real-time weather updates (planned).

## 🛠️ Tech Stack

### Frontend
*   **Framework**: React 18 (Vite)
*   **Language**: TypeScript
*   **Styling**: Tailwind CSS
*   **UI Components**: Shadcn UI, Radix UI, Lucide React
*   **State/animations**: Framer Motion, TanStack Query

### Backend
*   **Runtime**: Node.js
*   **Framework**: Express.js
*   **Database**: MongoDB (Mongoose)
*   **AI Providers**: Groq SDK (Llama 3.3-70b, Llama 3.2-90b-vision)
*   **Authentication**: JWT (JSON Web Tokens)
*   **File Handling**: Multer (Local storage)

## 📂 Project Structure

```
AgriTech_Web-main/
├── backend/                # Node.js/Express API
│   ├── src/
│   │   ├── config/         # Database config
│   │   ├── controllers/    # Route logic (Auth, Crop, AI)
│   │   ├── middlewares/    # Auth & Error handling
│   │   ├── models/         # Mongoose Schemas
│   │   ├── routes/         # API Endpoints
│   │   └── services/       # AI Integration (Groq)
│   ├── uploads/            # Image storage
│   └── app.js              # Entry point
│
├── frontend/               # React Application
│   ├── src/
│   │   ├── components/     # UI & Feature Components
│   │   │   ├── ai/         # Copilot/Chat interface
│   │   │   ├── disease/    # Scanner UI
│   │   │   └── ui/         # Shadcn Reusable components
│   │   ├── contexts/       # React Context (Auth, Lang)
│   │   ├── lib/            # Utilities
│   │   └── App.tsx         # Main Component
│   └── package.json
└── README.md
```

## ⚙️ Setup & Installation

### Prerequisites
*   Node.js (v18+)
*   MongoDB (Local or Atlas URI)
*   Groq API Key (for AI features)

### 1. Backend Setup
```bash
cd backend
npm install

# Create a .env file in the backend directory with:
# PORT=5000
# MONGO_URI=your_mongodb_connection_string
# JWT_SECRET=your_jwt_secret
# GROQ_API_KEY=your_groq_api_key

npm run dev
```

### 2. Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

## 🔌 Key API Endpoints

*   `POST /api/auth/register` - Create account
*   `POST /api/auth/login` - Login
*   `POST /api/crop/analyze` - Upload image for AI analysis
*   `POST /api/ai/copilot` - Chat with AI assistant
*   `GET /api/crop/history` - View past scans

## 🧠 AI Integration

The project uses a unified `aiService.js` to handle all AI requests:
*   **Text Generation**: Uses `llama-3.3-70b-versatile` for generating advice, fertilizer plans, and crop recommendations.
*   **Vision Analysis**: Uses `llama-3.2-90b-vision-preview` for analyzing uploaded crop images.