# Node.js Homework - Validation & Filtering (Module 03)

This project is an advanced Express.js server integrated with **MongoDB Atlas**. It features full CRUD operations for a notes collection, including advanced filtering, full-text search, pagination, and strict data validation.

## 🚀 Features

- **Advanced Filtering**: Filter notes by `tag` and perform full-text search using MongoDB text indexes.
- **Pagination**: Efficiently retrieve data using `page` and `perPage` query parameters.
- **Strict Validation**: All incoming requests are validated using **Celebrate** and **Joi**.
- **Full CRUD Operations**: Create, Read, Update, and Delete notes.
- **Database Integration**: Real-time data storage with MongoDB Atlas via Mongoose.
- **Enhanced Error Handling**: Integrated `http-errors` and `celebrate` error middleware for precise client feedback.

## 🛠️ Tech Stack

- **Runtime**: Node.js (v24.11.0)
- **Framework**: Express.js (v5.2.1)
- **Database**: MongoDB (via Mongoose)
- **Validation**: Celebrate / Joi
- **Logging**: Pino-http & Pino-pretty
- **Environment**: Dotenv

## 📂 Project Structure

```text
src/
├── constants/      # Global constants
├── controllers/    # Request handling logic
├── db/             # Database connection setup
├── middleware/     # Global error and 404 handlers, logging
├── models/         # Mongoose schemas (Note model)
├── routes/         # API endpoint definitions
├── validations/    # Joi validation schemas
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

### Query Parameters for `GET /notes`:
* **page:** Page number (default: 1)

* **perPage:** Items per page (5-20, default: 10)

* **tag:** Filter by specific tag (Work, Personal, etc.)

* **search:** Full-text search across title and content

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
