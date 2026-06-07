# 🎥 VidTube Backend

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-22.x-green)
![Express](https://img.shields.io/badge/Express.js-Backend-black)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-green)
![JWT](https://img.shields.io/badge/JWT-Authentication-blue)
![Cloudinary](https://img.shields.io/badge/Cloudinary-Media%20Storage-purple)
![License](https://img.shields.io/badge/License-ISC-orange)

A production-style backend for a video-sharing platform inspired by **YouTube + Twitter**, built using Node.js, Express, MongoDB, JWT Authentication, and Cloudinary.

</div>

---

## 🚀 Overview

VidTube is a scalable REST API that powers a modern video-sharing platform.

It provides:

- 🔐 Secure Authentication
- 🎥 Video Upload & Management
- ❤️ Likes System
- 💬 Comments
- 👥 Channel Subscriptions
- 📂 Playlists
- 🐦 Tweets / Community Posts
- 📊 Creator Dashboard Analytics
- ☁️ Cloudinary Media Storage

---

## ✨ Features

### 👤 User Management

- Register & Login
- JWT Authentication
- Refresh Token System
- Logout
- Change Password
- Update Profile
- Upload Avatar
- Upload Cover Image
- Watch History

### 🎬 Video Management

- Publish Videos
- Fetch Videos
- Update Video Metadata
- Delete Videos
- Toggle Publish Status
- Pagination Support

### 💬 Comments

- Add Comment
- Edit Comment
- Delete Comment
- Fetch Video Comments

### ❤️ Likes

- Like Videos
- Like Comments
- Like Tweets
- Fetch Liked Videos

### 📂 Playlists

- Create Playlist
- Update Playlist
- Delete Playlist
- Add Videos
- Remove Videos
- Fetch User Playlists

### 👥 Subscriptions

- Subscribe to Channels
- Fetch Subscribers
- Fetch Subscribed Channels

### 🐦 Tweets

- Create Tweet
- Update Tweet
- Delete Tweet
- Fetch User Tweets

### 📊 Dashboard

- Total Subscribers
- Total Views
- Total Likes
- Total Uploaded Videos

---

# 🏗️ Architecture

```text
Client
   │
   ▼
Routes
   │
   ▼
Controllers
   │
   ▼
Models
   │
   ▼
MongoDB
```

---

# 🛠️ Tech Stack

| Category | Technologies |
|-----------|-------------|
| Backend | Node.js, Express.js |
| Database | MongoDB, Mongoose |
| Authentication | JWT, bcrypt |
| Media Storage | Cloudinary |
| File Uploads | Multer |
| Utilities | dotenv, cors, cookie-parser |
| Development | Nodemon |

---

# 📁 Project Structure

```bash
src/
│
├── controllers/
│   ├── user.controller.js
│   ├── video.controller.js
│   ├── comment.controller.js
│   ├── like.controller.js
│   ├── playlist.controller.js
│   ├── subscription.controller.js
│   ├── tweet.controller.js
│   └── dashboard.controller.js
│
├── models/
├── routes/
├── middlewares/
├── db/
├── utils/
│
├── app.js
├── index.js
└── constants.js
```

---

# 🔐 Authentication Flow

```text
Login
   │
   ▼
Generate Access Token
Generate Refresh Token
   │
   ▼
Store Refresh Token
   │
   ▼
Protected Routes
   │
   ▼
Verify JWT Middleware
```

---

# 📦 Installation

### Clone Repository

```bash
git clone https://github.com/yourusername/vidtube-backend.git
cd vidtube-backend
```

### Install Dependencies

```bash
npm install
```

### Configure Environment Variables

Create a `.env` file:

```env
PORT=8000

MONGODB_URI=

CORS_ORIGIN=

ACCESS_TOKEN_SECRET=
ACCESS_TOKEN_EXPIRY=

REFRESH_TOKEN_SECRET=
REFRESH_TOKEN_EXPIRY=

CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
```

### Start Development Server

```bash
npm run dev
```

### Production

```bash
npm start
```

---

# 🌐 API Endpoints

## 👤 Users

| Method | Endpoint |
|----------|-----------|
| POST | /api/v1/users/register |
| POST | /api/v1/users/login |
| POST | /api/v1/users/logout |
| POST | /api/v1/users/refresh-token |
| GET | /api/v1/users/current-user |
| PATCH | /api/v1/users/update-account |
| PATCH | /api/v1/users/avatar |
| PATCH | /api/v1/users/cover-image |
| GET | /api/v1/users/history |

---

## 🎬 Videos

| Method | Endpoint |
|----------|-----------|
| GET | /api/v1/videos |
| POST | /api/v1/videos |
| GET | /api/v1/videos/:videoId |
| PATCH | /api/v1/videos/:videoId |
| DELETE | /api/v1/videos/:videoId |
| PATCH | /api/v1/videos/toggle/publish/:videoId |

---

## 💬 Comments

| Method | Endpoint |
|----------|-----------|
| GET | /api/v1/comments/:videoId |
| POST | /api/v1/comments/:videoId |
| PATCH | /api/v1/comments/c/:commentId |
| DELETE | /api/v1/comments/c/:commentId |

---

## ❤️ Likes

| Method | Endpoint |
|----------|-----------|
| POST | /api/v1/likes/toggle/v/:videoId |
| POST | /api/v1/likes/toggle/c/:commentId |
| POST | /api/v1/likes/toggle/t/:tweetId |
| GET | /api/v1/likes/videos |

---

## 📂 Playlists

| Method | Endpoint |
|----------|-----------|
| POST | /api/v1/playlist |
| GET | /api/v1/playlist/:playlistId |
| PATCH | /api/v1/playlist/:playlistId |
| DELETE | /api/v1/playlist/:playlistId |
| PATCH | /api/v1/playlist/add/:videoId/:playlistId |
| PATCH | /api/v1/playlist/remove/:videoId/:playlistId |

---

## 👥 Subscriptions

| Method | Endpoint |
|----------|-----------|
| GET | /api/v1/subscriptions/c/:channelId |
| POST | /api/v1/subscriptions/c/:channelId |
| GET | /api/v1/subscriptions/u/:subscriberId |

---

## 🐦 Tweets

| Method | Endpoint |
|----------|-----------|
| POST | /api/v1/tweets |
| GET | /api/v1/tweets/user/:userId |
| PATCH | /api/v1/tweets/:tweetId |
| DELETE | /api/v1/tweets/:tweetId |

---

## 📊 Dashboard

| Method | Endpoint |
|----------|-----------|
| GET | /api/v1/dashboard/stats |
| GET | /api/v1/dashboard/videos |

---

# 🧪 Sample Response

```json
{
  "statusCode": 200,
  "success": true,
  "message": "Video uploaded successfully",
  "data": {
    "title": "My First Video"
  }
}
```

---

# 🔮 Future Enhancements

- 🎥 Actual Video Streaming
- 🔎 Search Functionality
- 🔔 Notifications
- 📱 Mobile API Optimization
- 🐳 Docker Support
- 🧪 Unit Testing
- 📚 Swagger Documentation
- ⚡ Redis Caching
- 🤖 Recommendation System

---

# 👨‍💻 Author

### Aryan Yadav

Backend Developer • Full Stack Developer

- LinkedIn: https://www.linkedin.com/in/aryan-yadav-27766121b
- GitHub: https://github.com/clive-bixby

---

# ⭐ Support

If you found this project useful:

⭐ Star the repository

🍴 Fork it

🛠️ Contribute

---

<div align="center">

Built with ❤️ using Node.js & MongoDB

</div>
