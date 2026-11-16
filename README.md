# Diya — Intro to Backend Development CRUD Project

A learning project based on the freeCodeCamp **Intro to Backend Development** tutorial by Shivani / NewSmoke38.

**Tutorial:** https://www.youtube.com/watch?v=KOutPbKc9UM  
**Original source repository:** https://github.com/NewSmoke38/intro-to-backend

This repository is organized for local setup, practice, API testing and demonstration. The tutorial's core architecture and API behavior are retained; project metadata and this documentation have been personalized.

## What this project demonstrates

- Node.js project setup with npm
- Express application and route organization
- MongoDB Atlas connection using Mongoose
- User and Post models
- User registration, login and logout endpoints
- Password hashing and password comparison with bcrypt
- Post CRUD: Create, Read, Update and Delete
- API testing with Postman

## Project structure

```text
.
├── backend/
│   └── src/
│       ├── config/
│       │   ├── constants.js
│       │   └── database.js
│       ├── controllers/
│       │   ├── post.controller.js
│       │   └── user.controller.js
│       ├── models/
│       │   ├── post.model.js
│       │   └── user.model.js
│       ├── routes/
│       │   ├── post.route.js
│       │   └── user.route.js
│       ├── app.js
│       └── index.js
├── .env.example
├── .gitignore
├── package.json
└── README.md
```

## Requirements

- Node.js 18 or later
- npm
- MongoDB Atlas account and cluster
- Postman Desktop

## Setup

1. Open this project folder in VS Code.
2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a file named `.env` in the project root (same level as `package.json`).
4. Copy the contents of `.env.example` into `.env`.
5. Replace the placeholder with your MongoDB Atlas connection string:

   ```env
   PORT=4000
   MONGODB_URI="mongodb+srv://USERNAME:PASSWORD@YOUR_CLUSTER.mongodb.net/intro-to-backend?retryWrites=true&w=majority"
   ```

   Use your own Atlas database username, password and cluster address. Do not commit or share `.env`.

6. Start the development server:

   ```bash
   npm run dev
   ```

The server uses `http://localhost:4000` by default.

## API endpoints

Base URL: `http://localhost:4000`

### User endpoints

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/api/v1/users/register` | Register a user |
| POST | `/api/v1/users/login` | Log in a user |
| POST | `/api/v1/users/logout` | Log out a user |

Example registration body:

```json
{
  "username": "demo_user",
  "email": "demo@example.com",
  "password": "sample123"
}
```

Example login body:

```json
{
  "email": "demo@example.com",
  "password": "sample123"
}
```

### Post CRUD endpoints

| Method | Endpoint | CRUD operation |
|---|---|---|
| POST | `/api/v1/posts/create` | Create |
| GET | `/api/v1/posts/getPosts` | Read all |
| PATCH | `/api/v1/posts/update/:id` | Update by MongoDB ID |
| DELETE | `/api/v1/posts/delete/:id` | Delete by MongoDB ID |

Example create-post body:

```json
{
  "name": "Sample Post",
  "description": "Testing the post CRUD API",
  "age": 21
}
```

For Update and Delete, replace `:id` with the `_id` returned when a post is created or listed.

## Postman testing order

1. Register a user.
2. Log in using the same email and password.
3. Create a post.
4. Read all posts and copy the created post's `_id`.
5. Update the post using its ID.
6. Read all posts again to verify the change.
7. Delete the post using its ID.
8. Read all posts again to verify deletion.

## GitHub submission checklist

- [ ] Repository visibility is Public.
- [ ] Source files and README are committed.
- [ ] `.env.example` is committed.
- [ ] Actual `.env` is NOT committed.
- [ ] `node_modules/` is NOT committed.
- [ ] The server starts successfully on the local laptop.
- [ ] CRUD endpoints have been tested in Postman.

## Attribution

The backend tutorial and original implementation are by **Shivani (GitHub: NewSmoke38)** and were published through freeCodeCamp. This project is a learning adaptation of that tutorial. Please refer to the original repository and video for the tutorial source.
