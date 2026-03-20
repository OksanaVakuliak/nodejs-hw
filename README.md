# Node.js Homework - Email Reset & Avatar Upload (Module 05)

This project is a secure, production-ready Express.js server integrated with **MongoDB Atlas**. It implements a complete authentication system with user registration, login, session management via secure cookies, private data collections, password reset via email, and avatar image upload to Cloudinary.

## 🚀 Features

- **User Authentication**: Secure Registration and Login with password hashing via `bcrypt`.
- **Session Management**: Advanced session handling using `accessToken` and `refreshToken` stored in secure, `httpOnly` cookies.
- **Private Collections**: Each user has access only to their own notes. Data isolation is strictly enforced at the database level.
- **Advanced Filtering & Search**: Filter private notes by `tag` and perform full-text search.
- **Pagination**: Efficiently retrieve private data using `page` and `perPage` query parameters.
- **Strict Validation**: All authentication and note-related requests are validated using **Celebrate** and **Joi**.
- **Secure Architecture**: Implementation of an `authenticate` middleware to protect private routes.
- **Password Reset (Email)**: Request password reset links via email (Brevo / SMTP) and reset password using a time-limited JWT token.
- **Avatar Upload**: Upload user avatar images to Cloudinary (via memory upload + stream).

## 🛠️ Tech Stack

- **Runtime**: Node.js (v24.11.0)
- **Dev tools**: Nodemon (development server)
- **Framework**: Express.js (v5.2.1)
- **Database**: MongoDB (via Mongoose)
- **Validation**: Celebrate / Joi
- **Security**: Bcrypt (Hashing), Cookie-parser
- **Logging**: Pino-http & Pino-pretty
- **Environment**: Dotenv
- **Email**: Nodemailer (SMTP, configured for Brevo)
- **Templating**: Handlebars (email templates)
- **File Upload**: Multer (memoryStorage for uploads)
- **Cloud Storage**: Cloudinary (uploader stream)

## 📂 Project Structure

```text
src/
├── constants/      # Global constants
├── controllers/    # Request handling logic
├── db/             # Database connection setup
├── middleware/     # Auth, multer, Error handlers, 404, logging
├── models/         # Mongoose schemas (User, Session, Note)
├── routes/         # API endpoint definitions (auth, users, notes)
├── services/       # Auth logic (Sessions and Cookies)
├── templates/      # Email templates
├── utils/          # Helpers: sendMail.js, saveFileToCloudinary.js
├── validations/    # Joi validation schemas
└── server.js       # App entry point & middleware registration
```

## 📋 API Endpoints

### Authentication

| Method   | Endpoint                    | Description                              |
| :------- | :-------------------------- | :--------------------------------------- |
| **POST** | `/auth/register`            | Register a new user                      |
| **POST** | `/auth/login`               | Login user and create session            |
| **POST** | `/auth/refresh`             | Refresh access token using refresh token |
| **POST** | `/auth/logout`              | End session and clear cookies            |
| **POST** | `/auth/request-reset-email` | Request a password reset email           |
| **POST** | `/auth/reset-password`      | Reset password using token               |

### Notes (Private)

| Method     | Endpoint         | Description                    |
| :--------- | :--------------- | :----------------------------- |
| **GET**    | `/notes`         | Retrieve all notes             |
| **GET**    | `/notes/:noteId` | Retrieve a specific note by ID |
| **POST**   | `/notes`         | Create a new note              |
| **PATCH**  | `/notes/:noteId` | Update an existing note        |
| **DELETE** | `/notes/:noteId` | Delete a note by ID            |

### Users

| Method    | Endpoint           | Description                                  |
| :-------- | :----------------- | :------------------------------------------- |
| **PATCH** | `/users/me/avatar` | Upload or update authenticated user's avatar |

### Query Parameters for `GET /notes`:

- **page:** Page number (default: 1)

- **perPage:** Items per page (5-20, default: 10)

- **tag:** Filter by specific tag (Work, Personal, etc.)

- **search:** Full-text search across title and content

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

   Copy the example file and fill required values:

   ```bash
   cp .env.example .env
   # then edit .env and add your values
   ```

   Required environment variables are listed in `.env.example` and include:
   - `PORT` — server port (optional, default 3000)
   - `MONGO_URL` — MongoDB connection string
   - `JWT_SECRET` — secret for signing JWT tokens
   - `FRONTEND_DOMAIN` — frontend URL used in reset links
   - `CLOUDINARY_CLOUD_NAME`, `CLOUDINARY_API_KEY`, `CLOUDINARY_API_SECRET` — Cloudinary credentials
   - `SMTP_HOST`, `SMTP_PORT`, `SMTP_USER`, `SMTP_PASSWORD`, `SMTP_FROM` — SMTP (Brevo) settings

4. **Run the server:**

Development mode: `npm run dev`

Production mode: `npm start`

---

Developed by Oksana Vakuliak 💻

---
