# WebEtu - Student Portal

A full-stack web application for students to access their academic information including grades, schedules, attendance, and more.

## 🚀 Quick Start

### Prerequisites
- **Node.js** (v14 or higher)
- **npm** (v6 or higher)

### Installation & Run Locally

1. **Clone the repository**
```bash
git clone <your-repo-url>
cd webetu
```

2. **Install dependencies**
```bash
npm run install:all
```

3. **Start the development server** (Terminal 1)
```bash
npm run dev:server
```
The server runs on `http://localhost:5000`

4. **Start the React client** (Terminal 2)
```bash
npm start:client
```
The client runs on `http://localhost:3000`

5. **Open in browser**
Navigate to `http://localhost:3000`

---

## 📁 Project Structure

```
webetu/
├── server/                 # Express.js backend
│   ├── index.js           # Main server file
│   ├── package.json
│   └── routes/
│       ├── auth.js        # Authentication endpoints
│       └── student.js     # Student data endpoints
│
├── client/                # React frontend
│   ├── package.json
│   ├── public/
│   ├── src/
│   │   ├── App.js
│   │   ├── pages/         # Page components
│   │   ├── components/    # Reusable components
│   │   ├── context/       # React contexts
│   │   │   ├── AuthContext.js
│   │   │   ├── ThemeContext.js
│   │   │   └── LanguageContext.js
│   │   └── i18n/          # Internationalization
│   └── build/             # Production build
│
├── package.json           # Root package configuration
├── render.yaml            # Render deployment config
└── README.md             # This file
```

---

## 🔧 Available Scripts

### Root Level
```bash
npm run build              # Build for production
npm start                  # Start server only
npm run install:all        # Install all dependencies
npm run dev:server         # Start server in dev mode
npm run dev:client         # Start client in dev mode
```

### Client Level
```bash
cd client
npm start                  # Start React dev server
npm run build              # Build for production
npm test                   # Run tests
```

### Server Level
```bash
cd server
npm start                  # Start Express server
npm run dev               # Start with nodemon
```


## 🔐 Authentication

The app uses government API for authentication:
- **API:** `https://progres.mesrs.dz/api/authentication/v1/`
- **Login endpoint:** POST `/api/auth/login`
- **Required fields:** `username`, `password`

### Known Issues
- **Render Deployment:** The government API may block requests from Render's servers due to IP whitelisting
- **Solution:** Contact the API provider to whitelist your domain or IP range

---

## 🌐 Features

- 📚 **Dashboard** - Overview of academic info
- 📖 **BAC Notes** - Secondary school grades
- 📊 **Exam Grades** - Exam results
- 👥 **Groups** - Class groups and members
- 📅 **Timetable** - Class schedule
- 📋 **Inscriptions** - Course registrations
- 💼 **Internships** - Internship information
- 📄 **Bilans** - Academic reports
- 🎓 **Profile** - Student profile
- 🔔 **Absences** - Attendance records
- 🗓️ **Leave Requests** - Absence requests
- 🌙 **Dark Mode** - Dark/Light theme
- 🌍 **Multi-language** - English/Arabic support

---

## 🛠️ Technology Stack

### Frontend
- **React** - UI library
- **React Router** - Navigation
- **Axios** - HTTP client
- **Context API** - State management

### Backend
- **Express.js** - Web framework
- **Axios** - HTTP client
- **Helmet** - Security headers
- **CORS** - Cross-origin requests
- **Express Rate Limit** - API rate limiting

---

## 📝 Environment Variables

### Server (.env or Render config)
```
NODE_ENV=production
PORT=5000
```

---

## 🐛 Troubleshooting

### Login fails on Render
- The government API may be blocking Render's IP
- Try ngrok for local testing
- Contact API provider for IP whitelisting

### Port already in use
```bash
# Find process using port 5000
netstat -ano | findstr :5000

# Kill the process (Windows)
taskkill /PID <PID> /F
```

### Dependencies not installing
```bash
npm cache clean --force
npm run install:all
```

### Build fails
```bash
# Clear cache and reinstall
rm -r node_modules client/node_modules server/node_modules
npm run install:all
```

---

## 📧 Support

For issues or questions:
1. Check the logs in Render Dashboard
2. Test locally first with `npm run dev:server` and `npm start:client`
3. Use ngrok to debug API issues

---

## 📄 License

Private - Internal Use Only

---

## 👥 Team

Built with ❤️ for Student Portal
