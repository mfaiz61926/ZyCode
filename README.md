# ZyCode - DSA Coding Platform

A comprehensive full-stack Data Structures and Algorithms (DSA) coding platform similar to LeetCode, featuring problem solving, AI-powered assistance, video tutorials, and administrative tools.

## 🚀 Live Demo

[video link]

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Quick Start](#quick-start)
- [Project Structure](#project-structure)
- [API Documentation](#api-documentation)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This platform provides a complete coding interview preparation environment where users can:

- Solve DSA problems with an integrated code editor
- Get AI-powered hints and solutions using Google Gemini
- Watch video explanations for complex problems
- Track progress and submission history
- Practice with multiple programming languages

**Built for developers, by developers** - this platform combines the best features of modern coding platforms with AI assistance to accelerate learning.

## ✨ Features

### 🔐 User Management
- **Authentication**: JWT-based login/registration system
- **Role-based Access**: User and Admin roles with different permissions
- **Profile Management**: User profiles with progress tracking

### 📚 Problem Solving
- **Interactive Code Editor**: Monaco Editor with syntax highlighting
- **Multi-language Support**: C, C++, Java, JavaScript, Python
- **Real-time Testing**: Run code against visible test cases
- **Submission System**: Submit solutions with detailed feedback
- **Progress Tracking**: Track solved problems and submission history

### 🤖 AI-Powered Learning
- **Smart Assistance**: Context-aware help using Google Gemini AI
- **Code Review**: Get feedback on your solutions
- **Hint System**: Step-by-step guidance without spoilers
- **Algorithm Explanations**: Understand optimal approaches

### 🎥 Video Tutorials
- **Solution Videos**: Watch detailed explanations
- **Custom Player**: Built-in video player with progress tracking
- **Cloud Storage**: Optimized delivery via Cloudinary

### 👨‍💼 Admin Panel
- **Problem Management**: Create, update, and delete problems
- **Video Management**: Upload and manage solution videos
- **User Analytics**: Track platform usage and statistics
- **Content Validation**: Automatic validation of reference solutions

## 🛠 Tech Stack

### Frontend
- **React 18** with modern hooks
- **Redux Toolkit** for state management
- **React Router** for navigation
- **Monaco Editor** for code editing
- **DaisyUI + Tailwind** for styling
- **React Hook Form + Zod** for form validation

### Backend
- **Node.js + Express.js** for server
- **MongoDB** with Mongoose ODM
- **Redis** for caching and session management
- **JWT** for authentication
- **Judge0 API** for code execution

### External Services
- **Google Gemini AI** for intelligent assistance
- **Cloudinary** for video storage and processing
- **Judge0** for secure code execution

## 🏗 Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │   Backend       │    │  External APIs  │
│   (React SPA)   │◄──►│  (Express API)  │◄──►│  Judge0, Gemini │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Static Files  │    │   Database      │    │  Cloud Storage  │
│   (Vite Build)  │    │   (MongoDB)     │    │  (Cloudinary)   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## 🚀 Quick Start

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (running locally or cloud)
- Redis (for session management)
- Judge0 API key
- Google Gemini API key
- Cloudinary account (for video features)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/dsa-coding-platform.git
   cd dsa-coding-platform
   ```

2. **Backend Setup**
   ```bash
   cd backend
   npm install
   
   # Create .env file with required variables (see backend/README.md)
   cp .env.example .env
   
   # Start the backend server
   npm start
   ```

3. **Frontend Setup**
   ```bash
   cd ../frontend
   npm install
   
   # Create .env file
   echo "VITE_API_URL=http://localhost:3000" > .env
   
   # Start the development server
   npm run dev
   ```

4. **Access the Application**
   - Frontend: http://localhost:5173
   - Backend API: http://localhost:3000

### Environment Variables

**Backend (.env)**
```env
PORT=3000
DB_CONNECT_STRING=mongodb://localhost:27017/dsa-platform
JWT_KEY=your_jwt_secret
REDIS_PASS=your_redis_password
GEMINI_KEY=your_gemini_api_key
JUDGE0_API_KEY=your_judge0_api_key
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

**Frontend (.env)**
```env
VITE_API_URL=http://localhost:3000
```

## 📁 Project Structure

```
dsa-coding-platform/
├── frontend/                 # React frontend application
│   ├── src/
│   │   ├── components/       # Reusable UI components
│   │   ├── pages/           # Route components
│   │   ├── store/           # Redux store and slices
│   │   └── utils/           # Utility functions
│   ├── package.json
│   └── README.md            # Frontend-specific documentation
│
├── backend/                  # Node.js backend API
│   ├── controllers/         # Request handlers
│   ├── routes/             # API routes
│   ├── models/             # Database schemas
│   ├── middleware/         # Custom middleware
│   ├── config/             # Configuration files
│   ├── package.json
│   └── README.md           # Backend-specific documentation
│
├── docs/                   # Additional documentation (optional)
├── .gitignore
└── README.md              # This file
```

## 📡 API Documentation

### Authentication Endpoints
- `POST /user/register` - User registration
- `POST /user/login` - User login
- `POST /user/logout` - User logout
- `GET /user/check` - Validate session

### Problem Management
- `GET /problem/getAllProblem` - Fetch all problems
- `GET /problem/problemById/:id` - Get problem details
- `POST /problem/create` - Create problem (Admin)
- `PUT /problem/update/:id` - Update problem (Admin)

### Code Submission
- `POST /submission/run/:id` - Test code against visible cases
- `POST /submission/submit/:id` - Submit solution for evaluation

### AI Assistance
- `POST /ai/chat` - Get AI help for current problem

For detailed API documentation, see [backend/README.md](./backend/README.md)

## 📱 Screenshots

### Problem Solving Interface
![Problem Solving Interface](screenshots/problem-solving.png)

### AI Chat Assistant
![AI Chat](screenshots/ai-chat.png)

### Admin Panel
![Admin Panel](screenshots/admin-panel.png)

*Add screenshots to a `screenshots/` folder in your repository*

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes**
   - Follow the existing code style
   - Add tests if applicable
   - Update documentation as needed
4. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
5. **Push to your branch**
   ```bash
   git push origin feature/amazing-feature
   ```
6. **Open a Pull Request**

### Development Guidelines
- Follow the existing code structure
- Use meaningful commit messages
- Test your changes thoroughly
- Update relevant documentation
- Ensure responsive design for frontend changes

## 📋 Todo / Roadmap

- [ ] Real-time collaborative coding
- [ ] Contest and challenge system
- [ ] Social features (discussions, forums)
- [ ] Mobile app development
- [ ] Performance analytics dashboard
- [ ] Advanced AI tutoring features
- [ ] Multi-tenant support for organizations

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Contact

**Project Maintainer**: [Your Name]
- GitHub: [@yourusername](https://github.com/yourusername)
- Email: your.email@example.com
- LinkedIn: [Your LinkedIn](https://linkedin.com/in/yourprofile)

## 🙏 Acknowledgments

- **Judge0** for providing the code execution API
- **Google Gemini** for AI assistance capabilities  
- **Cloudinary** for video storage and processing
- **MongoDB** for reliable database services
- **Vercel/Netlify** for hosting solutions

---

⭐ **Star this repository if you found it helpful!**

*Built with ❤️ for the coding community*
