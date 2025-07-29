# 💡 AI Code Reviewer

A full-stack web application that allows developers to submit their code and receive intelligent, AI-powered feedback. The AI acts as a senior code reviewer, providing insights on code quality, performance, security, best practices, and maintainability.

## 🚀 Features

* 🧠 **AI-Powered Code Review** using Google Gemini (`gemini-2.0-flash`)
* 🖊️ Real-time code editing with syntax highlighting
* 📄 Markdown-based review rendering
* ⚡ Fast and responsive frontend using **React**
* 🌐 Express.js backend with structured API
* 🔐 Scalable architecture ready for production enhancements

---

## 🛠️ Tech Stack

| Frontend | Backend    | AI Model             | Libraries Used                                                                                 |
| -------- | ---------- | -------------------- | ---------------------------------------------------------------------------------------------- |
| React    | Express.js | Google Generative AI | `react-simple-code-editor`, `prismjs`, `rehype-highlight`, `axios`, `markdown`, `highlight.js` |

---

## 🖥️ Demo UI Overview

* **Left Panel**: Write or paste your JavaScript code.
* **Review Button**: Triggers an AI-based code analysis.
* **Right Panel**: Displays markdown-formatted review feedback from the AI.

---

## 🧠 How It Works

1. The user writes/pastes code into the editor.
2. On clicking **Review**, the frontend sends a POST request to `/ai/get-review`.
3. The backend routes the request through `ai.routes.js` and `ai.controller.js`.
4. `ai.service.js` uses the Google Gemini API to generate a detailed code review.
5. The AI’s response is sent back and rendered in markdown on the UI.

---

## 📁 Project Structure

```
.
├── frontend/
│   ├── App.jsx            # Main React Component
│   ├── App.css            # UI styling
│   ├── index.css          # Global styles
│   └── main.jsx           # Entry point
├── backend/
│   ├── app.js             # Express App Setup
│   ├── routes/
│   │   └── ai.routes.js   # API Route
│   ├── controllers/
│   │   └── ai.controller.js # Handles incoming code and sends to AI
│   └── services/
│       └── ai.service.js  # Google Gemini Integration
```

---

## ⚙️ Getting Started

### Prerequisites

* Node.js (v18+ recommended)
* Google Generative AI API Key (store in `.env` as `GOOGLE_GEMINI_KEY`)

---

### 🔧 Installation

#### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/ai-code-reviewer.git
cd ai-code-reviewer
```

#### 2. Setup Backend

```bash
cd backend
npm install
touch .env
# Add your key: GOOGLE_GEMINI_KEY=your_api_key_here
node app.js
```

#### 3. Setup Frontend

```bash
cd frontend
npm install
npm run dev
```

---

## 📌 Sample Prompt

```javascript
function fetchData() {
  let data = fetch('/api/data').then(response => response.json());
  return data;
}
```

AI Review Output:

* ❌ Handles async incorrectly.
* ✅ Suggested `async/await` version with error handling.

---

## 📬 API Endpoint

| Method | Route            | Description                                         |
| ------ | ---------------- | --------------------------------------------------- |
| POST   | `/ai/get-review` | Sends code to Gemini AI and returns markdown review |

---

## ✨ Future Enhancements

* ✅ Multi-language support (Python, Java, etc.)
* 🔍 Real-time linting with ESLint integration
* 💾 Save review history
* 📊 Dashboard for code quality insights

---

## 👨‍💻 Author

**Pratham** – [LinkedIn](https://www.linkedin.com/in/pratham-vidhani/)

---
