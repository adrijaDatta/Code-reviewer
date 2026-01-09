# 🤖 AI Code Reviewer

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=FFD62E)
![Gemini AI](https://img.shields.io/badge/Gemini_AI-1a472a?style=for-the-badge&logo=google&logoColor=white)

### Your Intelligent Code Review Assistant

*Leveraging Google Gemini AI for instant, actionable code feedback*

[![License: MIT](https://img.shields.io/badge/License-MIT-2d5016.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-2d5016.svg)](http://makeapullrequest.com)

[Features](#features) • [Installation](#installation) • [Usage](#usage) • [API Documentation](#api-documentation) • [Contributing](#contributing)

</div>

---

## 📋 Overview

AI Code Reviewer is a production-ready web application that integrates Google's Generative AI (Gemini) to provide intelligent, context-aware code analysis. Submit your source code and receive comprehensive feedback with syntax highlighting and markdown-formatted suggestions in real-time.

**Key Highlights:**
- ✅ Stateless architecture requiring no database
- ✅ RESTful API design for scalability
- ✅ Real-time AI-powered code analysis
- ✅ Beautiful syntax highlighting with PrismJS
- ✅ Clean markdown-rendered feedback

---

## ⚡ Features

### Core Functionality

```
┌─────────────────────────────────────────────────────────┐
│  Code Input  →  Gemini AI Analysis  →  Structured Review │
└─────────────────────────────────────────────────────────┘
```

**AI Analysis Engine**
- Powered by Google Gemini API for intelligent code review
- Context-aware suggestions and best practice recommendations
- Real-time processing with instant feedback

**Developer Experience**
- Syntax highlighting via PrismJS for enhanced readability
- Markdown rendering for clean, formatted output
- Responsive UI with optimized user flow
- Fast development with Vite build tooling

**Architecture**
- Fully stateless operation - no database required
- RESTful API with structured POST requests
- CORS-enabled for seamless frontend-backend communication
- Scalable Express.js backend infrastructure

---

## 🚀 Installation

### Prerequisites

```bash
Node.js v14 or higher
npm or yarn package manager
Google Gemini API Key
```

### Backend Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/ai-code-reviewer.git
cd ai-code-reviewer

# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Configure environment variables
cat > .env << EOF
GEMINI_API_KEY=your_api_key_here
PORT=3000
NODE_ENV=development
EOF

# Start the server
npm start
```

**Expected output:**
```
✓ Server running on http://localhost:3000
✓ Gemini AI initialized successfully
```

### Frontend Setup

```bash
# Navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

**Expected output:**
```
✓ Development server running on http://localhost:5173
✓ Connected to backend API
```

---

## 🛠️ Tech Stack

<table>
<tr>
<td width="50%" valign="top">

### Frontend

**Framework & Build Tools**
- **React.js** - Component-based UI library
- **Vite** - Next-generation frontend tooling
- **Axios** - Promise-based HTTP client

**UI & Rendering**
- **PrismJS** - Syntax highlighting engine
- **Markdown Renderer** - Formatted output display
- **Custom CSS** - Responsive design system

</td>
<td width="50%" valign="top">

### Backend

**Server & Framework**
- **Node.js** - JavaScript runtime environment
- **Express.js** - Minimal web framework
- **CORS** - Cross-origin middleware

**AI Integration**
- **Google Generative AI (Gemini)** - Code analysis engine
- **Structured API requests** - Optimized prompt engineering

</td>
</tr>
</table>

---

## 💡 Usage

### Starting the Application

```bash
# Terminal 1 - Start Backend
cd backend
npm start

# Terminal 2 - Start Frontend
cd frontend
npm run dev
```

### Workflow

1. **Access the Application**
   - Navigate to `http://localhost:5173` in your browser

2. **Submit Code for Review**
   - Paste your source code into the input editor
   - Select the programming language (optional)
   - Click "Review Code" button

3. **Review AI Feedback**
   - View syntax-highlighted code
   - Read structured suggestions and improvements
   - Access markdown-formatted best practices

### Example Review

**Input Code:**
```javascript
const express = require('express');
const aiRoutes = require('./routes/ai.routes')
const cors = require('cors')

const app = express()

app.use(cors())

app.use(express.json())

app.get('/', (req, res) => {
  res.send('Hello World')
})

app.use('/ai', aiRoutes)

module.exports = app
```

**AI-Generated Review Output:**
```markdown
✅ Current Codebase Issues

const express = require('express');
const aiRoutes = require('./routes/ai.routes')
const cors = require('cors')

const app = express()

app.use(cors())

app.use(express.json())

app.get('/', (req, res) => {
    res.send('Hello World')
})
```

*Comprehensive feedback includes code quality analysis, best practices, potential bugs, and optimization suggestions.*

---

## 🏗️ Project Structure

```
ai-code-reviewer/
│
├── backend/
│   ├── server.js              # Express server and API routes
│   ├── controllers/           # Request handlers
│   ├── services/              # Gemini AI integration
│   ├── package.json           # Backend dependencies
│   └── .env                   # Environment configuration
│
├── frontend/
│   ├── src/
│   │   ├── components/        # React components
│   │   │   ├── CodeEditor.jsx
│   │   │   ├── ReviewDisplay.jsx
│   │   │   └── SyntaxHighlight.jsx
│   │   ├── services/          # API communication
│   │   ├── App.jsx            # Main application
│   │   └── main.jsx           # Application entry point
│   ├── public/                # Static assets
│   ├── package.json           # Frontend dependencies
│   └── vite.config.js         # Vite configuration
│
└── README.md
```

---

## 📡 API Documentation

### Review Code Endpoint

**Endpoint:** `POST /api/review`

**Description:** Submits code to Gemini AI for comprehensive review and analysis.

**Request Headers:**
```
Content-Type: application/json
```

**Request Body:**
```json
{
  "code": "function calculateSum(a, b) {\n  return a + b;\n}",
  "language": "javascript"
}
```

**Success Response (200 OK):**
```json
{
  "success": true,
  "review": "## Code Review\n\n### Strengths\n- Clear function naming...",
  "timestamp": "2026-01-08T10:30:00Z"
}
```

**Error Response (400 Bad Request):**
```json
{
  "success": false,
  "error": "Code field is required",
  "timestamp": "2026-01-08T10:30:00Z"
}
```

**Error Response (500 Internal Server Error):**
```json
{
  "success": false,
  "error": "AI service temporarily unavailable",
  "timestamp": "2026-01-08T10:30:00Z"
}
```

---

## 🔑 Environment Variables

Create a `.env` file in the backend directory:

```bash
# Required
GEMINI_API_KEY=your_gemini_api_key_here

# Optional
PORT=3000
NODE_ENV=development
CORS_ORIGIN=http://localhost:5173
```

**Security Note:** Never commit your `.env` file to version control. Add it to `.gitignore`.

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

### Development Process

```bash
# 1. Fork the repository
# 2. Clone your fork
git clone https://github.com/yourusername/ai-code-reviewer.git

# 3. Create a feature branch
git checkout -b feature/your-feature-name

# 4. Make your changes and commit
git commit -m "Add: descriptive commit message"

# 5. Push to your fork
git push origin feature/your-feature-name

# 6. Open a Pull Request
```

### Commit Message Convention

- `Add:` New features
- `Fix:` Bug fixes
- `Update:` Updates to existing functionality
- `Refactor:` Code refactoring
- `Docs:` Documentation changes

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License - Free to use, modify, and distribute
```

---

## 👨‍💻 Author

**Adrija Datta**

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/yourusername)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/yourprofile)
[![Email](https://img.shields.io/badge/Email-2d5016?style=flat-square&logo=gmail&logoColor=white)](mailto:your.email@example.com)

---

## 🙏 Acknowledgments

- **Google AI Team** - For providing the Gemini API
- **React Community** - For excellent documentation and ecosystem
- **Vite Team** - For revolutionary build tooling
- **PrismJS** - For robust syntax highlighting
- **Open Source Contributors** - For inspiration and best practices

---

## 📊 Project Status

![Status](https://img.shields.io/badge/Status-Active-2d5016?style=flat-square)
![Maintenance](https://img.shields.io/badge/Maintained-Yes-2d5016?style=flat-square)
![Version](https://img.shields.io/badge/Version-1.0.0-1a472a?style=flat-square)

---

<div align="center">

**⭐ If you find this project useful, please consider giving it a star!**

Made with dedication and powered by AI

</div>
