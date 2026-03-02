# Node.js Homework - MongoDB & Mongoose Integration (Module 02)

This project is an evolution of the previous Express server, now integrated with **MongoDB Atlas** using **Mongoose**. The application follows a modular architecture, separating routes, controllers, models, and middleware for better maintainability.

## 🚀 Features

- **Full CRUD Operations**: Create, Read, Update, and Delete notes.
- **Database Integration**: Real-time data storage with MongoDB Atlas.
- **Modular Architecture**: Clean separation of concerns (Controllers, Services, Routes).
- **Validation**: Strict Mongoose schemas with `enum` tags and `timestamps`.
- **Enhanced Error Handling**: Integrated `http-errors` for specific status codes (404, 400).

## 🛠️ Tech Stack

- **Runtime**: Node.js (v24.11.0)
- **Framework**: Express.js (v5.2.1)
- **Database**: MongoDB (via Mongoose)
- **Logging**: Pino-http & Pino-pretty
- **Environment**: Dotenv

## 📂 Project Structure

```text
src/
├── controllers/    # Request handling logic
├── db/             # Database connection setup
├── middleware/     # Global error and 404 handlers, logging
├── models/         # Mongoose schemas (Note model)
├── routes/         # API endpoint definitions
└── server.js       # App entry point & middleware registration
```

## 📋 API Endpoints

| Method     | Endpoint         | Description                    |
| :--------- | :--------------- | :----------------------------- |
| **GET**    | `/notes`         | Retrieve all notes             |
| **GET**    | `/notes/:noteId` | Retrieve a specific note by ID |
| **POST**   | `/notes`         | Create a new note              |
| **PATCH**  | `/notes/:noteId` | Update an existing note        |
| **DELETE** | `/notes/:noteId` | Delete a note by ID            |

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
   MONGO_URL=mongodb+srv://<username>:<password>@cluster.mongodb.net/database_name
   ```

4. **Run the server:**

Development mode: `npm run dev`

Production mode: `npm start`

---

Developed by Oksana Vakuliak 💻

---
