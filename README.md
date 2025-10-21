# Association/Club Website

A modern, full-stack association/student club website built with Express.js backend and Next.js frontend.

## 📋 Features

### Backend
- ✅ User authentication (JWT)
- ✅ Blog/News management system
- ✅ Payment/Dues tracking system
- ✅ File upload (images, documents)
- ✅ RESTful API
- ✅ MongoDB database

### Frontend
- ✅ Modern and responsive design
- ✅ Next.js 15 (App Router)
- ✅ React 19
- ✅ TailwindCSS styling
- ✅ Dark mode support
- ✅ TypeScript support

## 🛠️ Technologies

**Backend:**
- Node.js & Express.js
- MongoDB & Mongoose
- JWT (JSON Web Tokens)
- Bcrypt (password hashing)
- Multer (file upload)

**Frontend:**
- Next.js 15
- React 19
- TypeScript
- TailwindCSS
- Axios

## 📦 Prerequisites

Before running the project, make sure you have the following installed:

- **Node.js** (v18 or higher) - [Download](https://nodejs.org/)
- **MongoDB** - [Local installation](https://www.mongodb.com/try/download/community) or [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) (free cloud)
- **npm** or **yarn** (comes with Node.js)

## 🚀 Installation and Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/ensaryesir/association_website.git
cd association_website
```

### 2️⃣ Backend Setup

```bash
# Navigate to backend folder
cd backend

# Install dependencies
npm install

# Create .env file
# Windows PowerShell:
Copy-Item .env.example .env

# Or manually copy .env.example and rename it to .env
```

#### Backend .env Configuration

Edit the `backend/.env` file:

```env
# MongoDB connection string
MONGODB_URI=mongodb://localhost:27017/association_db
# Or use MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/association_db

# JWT secret key (change this!)
JWT_SECRET=your_super_secret_jwt_key_change_this

# Server port
PORT=5000

# Environment
NODE_ENV=development
```

**Important:** Make sure to change the `JWT_SECRET` value! It should be a secure, random string.

#### Run the Backend

```bash
# Development mode (with auto-restart)
npm run dev

# Or production mode
npm start
```

Backend will run at: **http://localhost:5000**

### 3️⃣ Frontend Setup

Open a new terminal window:

```bash
# Navigate to frontend folder
cd frontend

# Install dependencies
npm install
```

#### Frontend Configuration (Optional)

If the backend is running on a different port, update the API services in `frontend/src/services/` folder.

#### Run the Frontend

```bash
# Start the development server
npm run dev
```

Frontend will run at: **http://localhost:3000**

## 📱 Usage

1. **Make sure the backend is running** (port 5000)
2. **Open the frontend in your browser** (http://localhost:3000)
3. Sign up or log in
4. Create blog posts, manage payments

## 📂 Project Structure

```
association_website/
├── backend/                 # Express.js API
│   ├── src/
│   │   ├── config/         # Database and other configurations
│   │   ├── middleware/     # Express middlewares
│   │   ├── models/         # MongoDB models
│   │   ├── routes/         # API routes
│   │   └── index.js        # Main entry file
│   ├── public/             # Uploaded files (in gitignore)
│   ├── .env                # Environment variables (in gitignore)
│   ├── .env.example        # Example environment variables
│   └── package.json
│
└── frontend/               # Next.js application
    ├── src/
    │   ├── app/           # Next.js App Router pages
    │   ├── components/    # React components
    │   ├── services/      # API requests
    │   ├── styles/        # CSS files
    │   ├── types/         # TypeScript types
    │   └── utils/         # Utility functions
    ├── public/            # Static files
    └── package.json
```

## 🔧 Development

### Backend Development

```bash
cd backend
npm run dev  # Auto-restart with nodemon
```

### Frontend Development

```bash
cd frontend
npm run dev  # Hot reload development
```

### Code Quality

ESLint and Prettier are configured in the frontend:

```bash
cd frontend
npm run lint  # Code checking
```

## 🏗️ Production Build

### Frontend Build

```bash
cd frontend
npm run build
npm start  # Run in production mode
```

## 🗄️ Database

The project uses **MongoDB**. You have two options:

### Local MongoDB (Recommended - Development)

1. Download [MongoDB Community Server](https://www.mongodb.com/try/download/community)
2. Install and start it
3. In `.env` file: `MONGODB_URI=mongodb://localhost:27017/association_db`

### MongoDB Atlas (Cloud - Free)

1. Create an account on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a free cluster
3. Copy the connection string
4. Add to `.env` file: `MONGODB_URI=mongodb+srv://...`

## 📸 API Endpoints

### Auth
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user information

### Blog
- `GET /api/blog` - Get all blog posts
- `GET /api/blog/:id` - Get single blog post
- `POST /api/blog` - Create new blog post (authentication required)
- `PUT /api/blog/:id` - Update blog post (authentication required)
- `DELETE /api/blog/:id` - Delete blog post (authentication required)

### Payments
- `GET /api/payments` - Get payment list
- `POST /api/payments` - Create new payment record
- Check the backend code for additional endpoints

## ⚠️ Troubleshooting

### MongoDB connection error

```
Error: connect ECONNREFUSED 127.0.0.1:27017
```

**Solution:**
- Make sure MongoDB service is running
- Windows: Check "MongoDB Server" in Services
- Verify `MONGODB_URI` in `.env` file is correct

### Port already in use

```
Error: listen EADDRINUSE: address already in use :::5000
```

**Solution:**
```powershell
# Find the process using the port in Windows PowerShell
netstat -ano | findstr :5000

# Kill the process (use the PID from the command above)
taskkill /PID <PID_NUMBER> /F
```

### node_modules issues

```bash
# Clean cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

## 📝 License

This project is licensed under the [MIT License](LICENSE).


**Note:** On first run, the `public/uploads` folder will be automatically created in the backend. This folder is used for uploaded files.
