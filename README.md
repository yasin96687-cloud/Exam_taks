# Task API

A simple Task API built with Node.js, Express, MongoDB and Mongoose.

## Setup
1. Install Node.js and MongoDB.
2. Run `npm install`.
3. Copy `.env.example` to `.env` and set `MONGO_URI`.
4. Run `npm run dev` or `npm start`.

## Create a task
`POST /api/tasks`

JSON body:
```json
{
  "title": "Finish assignment",
  "status": "pending",
  "dueDate": "2026-12-01",
  "userId": "PUT_A_REAL_USER_OBJECT_ID_HERE"
}
```
Returns HTTP 201 on success and HTTP 400 for invalid input.

## Get tasks
`GET /api/tasks?page=1&limit=10&status=done`

The `status` filter is optional. Response includes `total`, `page`, `limit`, and `data`.

Note: `userId` references a User collection. Create a User document first and use its MongoDB ObjectId.
