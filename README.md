# Social.ly 🌐

A full-stack social media web application built with the MERN stack (MongoDB, Express.js, React, Node.js). Social.ly provides a modern, real-time social networking experience with features like posts, comments, messaging, notifications, and user profiles.

## ✨ Features

- **User Authentication**: Secure registration and login with JWT tokens and OTP verification
- **Posts & Interactions**: Create, edit, delete posts with like and save functionality
- **Comments & Replies**: Multi-level commenting system with nested replies
- **Real-time Messaging**: Chat with other users using Socket.IO for instant communication
- **Notifications**: Stay updated with real-time notifications for likes, comments, and follows
- **User Profiles**: Customizable profiles with bio, profile picture, and activity tracking
- **Search Functionality**: Find users and content across the platform
- **Responsive Design**: Mobile-friendly interface that works on all devices

## 🏗️ Project Structure

```
Social.ly/
├── backend/                    # Express.js server and APIs
│   ├── server.js              # Entry point with Socket.IO setup
│   ├── app.js                 # Express app configuration
│   ├── config/                # Configuration files
│   │   └── db.js             # MongoDB connection
│   ├── controllers/           # Business logic
│   │   ├── userController.js
│   │   ├── postController.js
│   │   └── chatController.js
│   ├── models/                # Mongoose schemas
│   │   ├── userModel.js
│   │   ├── postModel.js
│   │   ├── commentModel.js
│   │   ├── messageModel.js
│   │   └── notificationModel.js
│   ├── routes/                # API routes
│   ├── middleware/            # Custom middleware (auth, email)
│   └── utils/                 # Helper functions
│
└── frontend/                   # React application
    ├── src/
    │   ├── Components/        # Reusable UI components
    │   │   ├── Cards/
    │   │   ├── Messages/
    │   │   ├── Modals/
    │   │   └── Sidebar/
    │   ├── pages/             # Page components
    │   │   ├── Home/
    │   │   ├── Profile/
    │   │   ├── Messages/
    │   │   └── Notifications/
    │   ├── redux/             # State management
    │   ├── routes/            # Routing configuration
    │   ├── hooks/             # Custom React hooks
    │   └── styles/            # CSS stylesheets
    └── public/
```

## ⚙️ Tech Stack

### Frontend
- **React** - UI library
- **React Router DOM** - Client-side routing
- **Redux Toolkit** - State management
- **Axios** - HTTP client
- **Socket.IO Client** - Real-time communication
- **React Toastify** - Toast notifications
- **Lucide React** - Icon library
- **date-fns** - Date formatting

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB ODM
- **Socket.IO** - WebSocket library for real-time features
- **JWT** - Authentication tokens
- **bcrypt** - Password hashing
- **Nodemailer** - Email service
- **Cloudinary** - Image upload and storage
- **Cookie Parser** - Parse cookies
- **CORS** - Cross-origin resource sharing

## � Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas account)
- **Git**

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/<your-username>/Social.ly.git
cd Social.ly
```

### 2️⃣ Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the backend directory with the following variables:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGO_URI=mongodb://localhost:27017/socialy
DB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/socialy

# JWT Secret
JWT_SECRET=your_super_secret_jwt_key_here

# Frontend URLs
LOCAL_URL=http://localhost:3000
WEB_URL=https://your-production-domain.com

# Cloudinary Configuration (for image uploads)
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Email Configuration (Nodemailer)
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password
```

4. Start the backend server:
```bash
npm run dev
```

The backend server will run on `http://localhost:5000`

### 3️⃣ Frontend Setup

1. Open a new terminal and navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the frontend directory:

```env
REACT_APP_BACKEND_URL=http://localhost:5000
```

4. Start the frontend development server:
```bash
npm start
```

The frontend will run on `http://localhost:3000` and automatically open in your browser.

## � Configuration Details

### MongoDB Setup
- **Local MongoDB**: Install MongoDB locally and use `mongodb://localhost:27017/socialy`
- **MongoDB Atlas**: Create a free cluster at [mongodb.com/atlas](https://www.mongodb.com/atlas) and use the connection string

### Cloudinary Setup
1. Create a free account at [cloudinary.com](https://cloudinary.com/)
2. Get your credentials from the dashboard
3. Add them to your backend `.env` file

### Email Configuration
1. For Gmail, enable 2-factor authentication
2. Generate an App Password from Google Account settings
3. Use the App Password in the `EMAIL_PASS` variable

## 📜 Available Scripts

### Backend
```bash
npm run dev      # Start development server with nodemon (auto-reload)
```

### Frontend
```bash
npm start        # Start development server
npm run build    # Create production build
npm test         # Run tests
npm run eject    # Eject from Create React App (irreversible)
```

## 🔗 API Endpoints

### Authentication
- `POST /api/users/register` - Register new user
- `POST /api/users/login` - User login
- `POST /api/users/verify-otp` - Verify OTP
- `POST /api/users/logout` - User logout

### Posts
- `GET /api/posts` - Get all posts
- `POST /api/posts` - Create new post
- `PUT /api/posts/:id` - Update post
- `DELETE /api/posts/:id` - Delete post
- `POST /api/posts/:id/like` - Like/unlike post
- `POST /api/posts/:id/save` - Save/unsave post

### Comments
- `POST /api/comments/:postId` - Add comment to post
- `GET /api/comments/:postId` - Get post comments
- `DELETE /api/comments/:id` - Delete comment

### Chat
- `GET /api/chat` - Get user chats
- `POST /api/chat` - Send message
- `GET /api/chat/:userId` - Get chat with specific user

## 🚀 Deployment

### Frontend Deployment (Vercel/Netlify)
1. Build the production bundle:
```bash
cd frontend
npm run build
```
2. Deploy the `build` folder to Vercel or Netlify
3. Set environment variable: `REACT_APP_BACKEND_URL=<your-backend-url>`

### Backend Deployment (Render/Railway/Heroku)
1. Push your code to GitHub
2. Connect your repository to your hosting platform
3. Set all environment variables from `.env`
4. Deploy the backend service

### Environment Variables for Production
- Update `NODE_ENV=production`
- Update `WEB_URL` to your frontend domain
- Use production MongoDB URI (`DB_URI`)

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and development process.

## 📋 Code of Conduct

Please read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for details on our code of conduct.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## 🐛 Known Issues & Troubleshooting

### Common Issues

**MongoDB Connection Error**
- Ensure MongoDB is running locally or check your Atlas connection string
- Verify your IP is whitelisted in MongoDB Atlas

**CORS Errors**
- Check that `LOCAL_URL` and `WEB_URL` in backend `.env` match your frontend URL
- Ensure CORS is properly configured in `app.js`

**Socket.IO Connection Issues**
- Verify Socket.IO versions match in frontend and backend
- Check that the backend URL is correctly set in frontend

**Image Upload Failures**
- Verify Cloudinary credentials are correct
- Check file size limits and supported formats

## 📞 Support

If you encounter any issues or have questions:
- Open an issue on GitHub
- Check existing issues for solutions
- Review the documentation thoroughly

## 🌟 Show Your Support

If you find this project helpful, please give it a ⭐ on GitHub!

---

**Happy Coding! 🚀**

