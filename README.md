# Node.js Homework - Express Server (Module 01)

A basic Express.js web server created to demonstrate fundamental backend skills, including routing, middleware integration, and error handling.

## 🔗 Live Demo
**API URL:** [https://nodejs-hw-w025.onrender.com](https://nodejs-hw-w025.onrender.com)

## 🚀 Features

- **RESTful API**: Basic routes for managing notes.
- **Logging**: Request logging using `pino-http` and `pino-pretty`.
- **Security**: CORS enabled for cross-origin requests.
- **Error Handling**: Custom global error middleware and 404 route handling.
- **Environment Variables**: Port configuration via `.env`.

## 🛠️ Tech Stack

- **Node.js** (v24.11.0)
- **Express.js** (v5.2.1)
- **Pino** (Logging)
- **Dotenv** (Environment management)

## 📋 API Endpoints

| Method  | Endpoint         | Description                    |
| :------ | :--------------- | :----------------------------- |
| **GET** | `/notes`         | Retrieve all notes             |
| **GET** | `/notes/:noteId` | Retrieve a specific note by ID |
| **GET** | `/test-error`    | Simulate a 500 Server Error    |

## ⚙️ Installation & Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/OksanaVakuliak/nodejs-hw.git
   cd nodejs-hw
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Configure Environment Variables:** Create a .env file in the root directory:

   ```bash
   PORT=3000
   ```

4. **Run the server:**

Development mode: `npm run dev`

Production mode: `npm start`

---

Developed by Oksana Vakuliak 💻

---
