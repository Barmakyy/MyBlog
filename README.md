[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=19931942&assignment_repo_type=AssignmentRepo)

# MERN Stack Blog Application

A full-stack blog application built with the MERN stack (MongoDB, Express.js, React, Node.js) featuring user authentication, CRUD operations for blog posts, and modern UI with dark/light theme support.

## 🚀 Live Applications

### Frontend Application
- **URL**: [https://myblog-1-3sfd.onrender.com/]  
- **Platform**: Render
- **Status**: ✅ Deployed

### Backend API
- **URL**: [https://myblog-xv15.onrender.com](https://myblog-xv15.onrender.com)
- **API Base**: [https://myblog-xv15.onrender.com/api](https://myblog-xv15.onrender.com/api)
- **Platform**: Render
- **Status**: ✅ Deployed

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [Deployment](#deployment)
- [CI/CD Pipeline](#cicd-pipeline)
- [Monitoring](#monitoring)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

### Core Features
- 🔐 **User Authentication**: JWT-based authentication with registration and login
- 📝 **Blog Posts**: Create, read, update, and delete blog posts
- 🏷️ **Categories**: Organize posts by categories
- 🔍 **Search**: Search posts by title and content
- 📄 **Pagination**: Efficient pagination for large datasets
- 🌓 **Theme Support**: Dark and light theme toggle
- 📱 **Responsive Design**: Mobile-first responsive design

### Advanced Features
- 🛡️ **Security**: Input validation, rate limiting, CORS protection
- 📊 **Error Handling**: Comprehensive error handling and logging
- 🔄 **Real-time Updates**: Optimistic UI updates
- 📈 **Performance**: Optimized queries and caching strategies

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI library
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Utility-first CSS framework
- **React Router** - Client-side routing
- **Axios** - HTTP client
- **Context API** - State management

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB ODM
- **JWT** - Authentication
- **bcryptjs** - Password hashing
- **cors** - Cross-origin resource sharing
- **helmet** - Security middleware

### DevOps & Deployment
- **GitHub Actions** - CI/CD pipeline
- **Render** - Backend hosting
- **Vercel** - Frontend hosting
- **MongoDB Atlas** - Cloud database

## 📁 Project Structure

```
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── contexts/       # React contexts
│   │   ├── hooks/          # Custom hooks
│   │   ├── services/       # API services
│   │   └── assets/         # Static assets
│   ├── public/             # Public assets
│   └── package.json
├── server/                 # Backend Node.js application
│   ├── controllers/        # Route controllers
│   ├── middleware/         # Custom middleware
│   ├── models/             # Mongoose models
│   ├── routes/             # API routes
│   └── package.json
├── deployment/             # Deployment configuration
│   ├── config/             # Platform-specific configs
│   └── scripts/            # Deployment scripts
├── monitoring/             # Monitoring and health checks
├── .github/workflows/      # GitHub Actions workflows
├── env.example             # Environment variables template
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn
- MongoDB Atlas account
- Git

### Local Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/mern-blog-app.git
   cd mern-blog-app
   ```

2. **Install dependencies**
   ```bash
   # Install backend dependencies
   cd server
   npm install
   
   # Install frontend dependencies
   cd ../client
   npm install
   ```

3. **Set up environment variables**
   ```bash
   # Copy environment template
   cp env.example .env
   
   # Edit .env file with your configuration
   nano .env
   ```

4. **Start the development servers**
   ```bash
   # Start backend server (from server directory)
   npm run dev
   
   # Start frontend server (from client directory)
   npm run dev
   ```

5. **Access the application**
   - Frontend: http://localhost:5173
   - Backend API: http://localhost:5000

## 🔧 Environment Variables

Copy `env.example` to `.env` and configure the following variables:

### Required Variables
```env
# Database
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/database

# Authentication
JWT_SECRET=your_super_secret_jwt_key

# Server
PORT=5000
NODE_ENV=development

# CORS
CORS_ORIGIN=http://localhost:5173
```

### Optional Variables
```env
# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100

# Logging
LOG_LEVEL=info

# JWT
JWT_EXPIRES_IN=7d
```

## 🚀 Deployment

### Backend Deployment (Render)

1. **Create a Render account** at [render.com](https://render.com)

2. **Connect your GitHub repository**

3. **Create a new Web Service**
   - **Build Command**: `cd server && npm ci && npm run build`
   - **Start Command**: `cd server && npm start`
   - **Environment**: Node

4. **Configure environment variables** in Render dashboard:
   - `MONGODB_URI`
   - `JWT_SECRET`
   - `NODE_ENV=production`
   - `CORS_ORIGIN=https://your-frontend-domain.vercel.app`

5. **Deploy** - Render will automatically deploy on every push to main branch

### Frontend Deployment (Vercel)

1. **Create a Vercel account** at [vercel.com](https://vercel.com)

2. **Import your GitHub repository**

3. **Configure build settings**:
   - **Framework Preset**: Vite
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
   - **Install Command**: `npm ci`

4. **Set environment variables**:
   - `VITE_API_URL=https://your-backend-domain.onrender.com/api`

5. **Deploy** - Vercel will automatically deploy on every push to main branch

### Alternative Deployment Options

#### Backend Alternatives
- **Railway**: [railway.app](https://railway.app)
- **Heroku**: [heroku.com](https://heroku.com)
- **DigitalOcean App Platform**: [digitalocean.com](https://digitalocean.com)

#### Frontend Alternatives
- **Netlify**: [netlify.com](https://netlify.com)
- **GitHub Pages**: [pages.github.com](https://pages.github.com)
- **Firebase Hosting**: [firebase.google.com](https://firebase.google.com)

## 🔄 CI/CD Pipeline

This project uses GitHub Actions for continuous integration and deployment.

### Pipeline Overview

```mermaid
graph LR
    A[Push to Main] --> B[Run Tests]
    B --> C[Build Applications]
    C --> D[Deploy Backend]
    C --> E[Deploy Frontend]
    D --> F[Health Checks]
    E --> F
    F --> G[Notify Team]
```

### Workflow Steps

1. **Backend CI**
   - Install dependencies
   - Run linting
   - Execute tests
   - Build application

2. **Frontend CI**
   - Install dependencies
   - Run linting
   - Execute tests
   - Build application
   - Upload build artifacts

3. **Deployment**
   - Deploy backend to Render
   - Deploy frontend to Vercel
   - Run health checks
   - Send notifications

### Screenshots

#### CI/CD Pipeline in Action
![GitHub Actions Workflow](https://via.placeholder.com/800x400/0066cc/ffffff?text=CI/CD+Pipeline+Screenshot)

#### Deployment Status
![Deployment Status](https://via.placeholder.com/800x400/00cc66/ffffff?text=Deployment+Status)

## 📊 Monitoring

### Health Checks

The application includes automated health checks that monitor:

- **Backend API endpoints**
- **Frontend accessibility**
- **Database connectivity**
- **Response times**

### Monitoring Script

Run health checks manually:
```bash
# Single health check
node monitoring/health-check.js --once

# Continuous monitoring
node monitoring/health-check.js --monitor
```

### Monitoring Setup

1. **Uptime Monitoring**: Set up uptime monitoring with services like:
   - [UptimeRobot](https://uptimerobot.com)
   - [Pingdom](https://pingdom.com)
   - [StatusCake](https://statuscake.com)

2. **Error Tracking**: Integrate error tracking with:
   - [Sentry](https://sentry.io)
   - [LogRocket](https://logrocket.com)
   - [Bugsnag](https://bugsnag.com)

3. **Performance Monitoring**: Monitor application performance with:
   - [New Relic](https://newrelic.com)
   - [DataDog](https://datadoghq.com)
   - [AppDynamics](https://appdynamics.com)

## 📚 API Documentation

### Authentication Endpoints

#### Register User
```http
POST /api/auth/register
Content-Type: application/json

{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "password123"
}
```

#### Login User
```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "password123"
}
```

### Posts Endpoints

#### Get All Posts
```http
GET /api/posts?page=1&limit=10&category=tech
Authorization: Bearer <token>
```

#### Create Post
```http
POST /api/posts
Authorization: Bearer <token>
Content-Type: application/json

{
  "title": "My First Blog Post",
  "content": "This is the content of my blog post...",
  "category": "60f7b3b3b3b3b3b3b3b3b3b3"
}
```

#### Update Post
```http
PUT /api/posts/:id
Authorization: Bearer <token>
Content-Type: application/json

{
  "title": "Updated Blog Post Title",
  "content": "Updated content..."
}
```

#### Delete Post
```http
DELETE /api/posts/:id
Authorization: Bearer <token>
```

### Categories Endpoints

#### Get All Categories
```http
GET /api/categories
```

#### Create Category
```http
POST /api/categories
Authorization: Bearer <token>
Content-Type: application/json

{
  "name": "Technology",
  "description": "Tech-related posts"
}
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow the existing code style
- Write tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting PR

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [React](https://reactjs.org/) - A JavaScript library for building user interfaces
- [Express.js](https://expressjs.com/) - Fast, unopinionated, minimalist web framework
- [MongoDB](https://www.mongodb.com/) - The database for modern applications
- [Tailwind CSS](https://tailwindcss.com/) - A utility-first CSS framework
- [Vite](https://vitejs.dev/) - Next Generation Frontend Tooling

## 📞 Support

If you have any questions or need help with the application:

- **Issues**: [GitHub Issues](https://github.com/yourusername/mern-blog-app/issues)
- **Email**: your-email@example.com
- **Documentation**: [Wiki](https://github.com/yourusername/mern-blog-app/wiki)

---

**Made with ❤️ by [Your Name]**
