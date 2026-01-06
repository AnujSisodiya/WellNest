# WellNest

WellNest is a health and wellness platform designed to connect health experts with users. Built with the MERN (MongoDB, Express, React, Node.js) stack, it enables users to build communities, seek consultations for minor health issues, and share wellness advice.

## Features

- **User Authentication**: Secure signup and login with JWT and email OTP verification.
- **Social Feed**: Create, view, and delete posts.
- **Real-time Chat**: Private messaging between users using Socket.io.
- **Communities**: Join and participate in community groups.
- **Profile Management**: View and manage user profiles and posts.
- **Search**: Search for other users by name or email.

## Tech Stack

### Client
- **React**: UI library for building the frontend.
- **Redux**: State management (to be confirmed, but standard in this stack).
- **Tailwind CSS**: Utility-first CSS framework for styling.
- **Socket.io-client**: Real-time communication library.
- **React Router**: Client-side routing.

### Server
- **Node.js & Express**: Backend runtime and framework.
- **MongoDB & Mongoose**: NoSQL database and object modeling.
- **Socket.io**: Real-time event-based communication.
- **JWT**: JSON Web Tokens for authentication.
- **Nodemailer**: For sending OTP emails.

## Prerequisites

- **Node.js**: (v14 or higher recommended)
- **MongoDB**: (Local instance or Atlas connection)

## Installation & Setup

1.  **Clone the repository**
    ```bash
    git clone <repository-url>
    cd connectify
    ```

2.  **Install Server Dependencies**
    ```bash
    npm install
    ```

3.  **Install Client Dependencies**
    ```bash
    cd client
    npm install
    cd ..
    ```

4.  **Environment Configuration**
    Create a `.env` file in the root directory with the following variables:
    ```env
    PORT=4000
    MONGODB_URL=mongodb://localhost:27017/connectify
    JWT_SECRET=your_super_secret_key
    MAIL_HOST=smtp.gmail.com
    MAIL_USER=your_email@gmail.com
    MAIL_PASS=your_email_app_password
    ```

5.  **Run the Application**
    
    Start the backend server:
    ```bash
    npm run dev
    ```

    In a new terminal, start the frontend client:
    ```bash
    cd client
    npm start
    ```

    The client will run on `http://localhost:3000` and the server on `http://localhost:4000`.

## API Endpoints

### Authentication (`/api/auth`)
- `POST /signup`: Register a new user.
- `POST /login`: Authenticate user and get token.
- `POST /sendotp`: Send OTP for email verification.
- `POST /user`: Get user details by ID.

### Posts (`/api/auth`)
- `GET /posts`: Get all posts.
- `POST /posts`: Create a new post.
- `GET /myposts`: Get current user's posts.
- `DELETE /posts/:postId`: Delete a post.

### Chat (`/chat`)
- `POST /`: Create a new chat.
- `GET /:userId`: Get all chats for a user.
- `GET /find/:firstId/:secondId`: Find chat between two users.

### Message (`/message`)
- `POST /`: Send a message.
- `GET /:chatId`: Get messages for a chat.

### Community (`/community`)
- `POST /create`: Create a new community.
- `POST /join`: Join a community.
- `GET /`: Get all communities.
- `GET /:communityId/group`: Get community messages.

## Folder Structure

```
connectify/
├── client/                 # React Frontend
│   ├── public/
│   └── src/
│       ├── components/     # UI Components
│       ├── routers/        # Route Definitions
│       └── ...
├── server/                 # Express Backend
│   ├── config/             # Database config
│   ├── controllers/        # Route logic
│   ├── middlewares/        # Auth middleware
│   ├── models/             # Mongoose models
│   ├── routes/             # API routes
│   └── ...
└── socket/                 # Socket.io logic
```
