# 💬 Realtime Chat App

A full-stack real-time chat application built with the MERN stack and Socket.IO. It supports instant one-on-one messaging, online presence indicators, image sharing, profile customization, and a fully themeable UI with 30+ DaisyUI themes.

---

## ✨ Features

- 🔐 **JWT Authentication** — Secure signup, login, and logout with HTTP-only cookies
- ⚡ **Real-time Messaging** — Instant message delivery powered by Socket.IO
- 🟢 **Online User Tracking** — See who's currently online in real time
- 🖼️ **Image Sharing** — Send images in chat, stored and served via Cloudinary
- 👤 **Profile Management** — Update your profile picture (uploaded to Cloudinary)
- 🎨 **30+ Themes** — Full DaisyUI theme support with live preview in Settings
- 📱 **Responsive Design** — Works seamlessly across all screen sizes

---

## 🛠️ Tech Stack

### Backend
| Technology | Purpose |
|---|---|
| Node.js + Express 5 | REST API server |
| MongoDB + Mongoose | Database & ODM |
| Socket.IO | WebSocket-based real-time communication |
| JSON Web Tokens (JWT) | Stateless authentication |
| bcryptjs | Password hashing |
| Cloudinary | Cloud image storage |
| cookie-parser | HTTP cookie handling |
| dotenv | Environment variable management |
| nodemon | Dev server with hot reload |

### Frontend
| Technology | Purpose |
|---|---|
| React 18 + Vite | UI framework & build tool |
| React Router DOM v6 | Client-side routing |
| Zustand | Lightweight global state management |
| Socket.IO Client | Real-time WebSocket connection |
| Axios | HTTP API requests |
| Tailwind CSS v3 | Utility-first styling |
| DaisyUI | Themed UI component library |
| lucide-react | Icon library |
| react-hot-toast | Toast notifications |

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** v18+
- **MongoDB** (local instance or MongoDB Atlas URI)
- **Cloudinary** account (for image uploads)

### Environment Variables

Create a `.env` file inside the `backend/` directory:

```env
PORT=5001
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

### Installation & Running Locally

```bash
# 1. Clone the repository
git clone https://github.com/vardaansinghal17/REALTIME-CHAT-APP.git
cd REALTIME-CHAT-APP

# 2. Install backend dependencies
cd backend
npm install

# 3. Install frontend dependencies
cd ../frontend
npm install

# 4. Start the backend (from root or backend/)
cd ../backend
npm run dev

# 5. Start the frontend (in a separate terminal)
cd ../frontend
npm run dev
```

- **Frontend** runs at: `http://localhost:5173`
- **Backend** runs at: `http://localhost:5001`

---

## 📦 Production Build

From the project root, a single command installs all dependencies and builds the frontend:

```bash
npm run build
npm start
```

In production mode, the Express server serves the compiled React frontend statically.

---

## 🔌 API Endpoints

### Auth Routes — `/api/auth`
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/signup` | Register a new user |
| `POST` | `/login` | Login with email & password |
| `POST` | `/logout` | Clear auth cookie & logout |
| `PUT` | `/update-profile` | Update profile picture |
| `GET` | `/check` | Verify current auth session |

### Message Routes — `/api/messages`
| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/users` | Get all users for the sidebar |
| `GET` | `/:id` | Get conversation with a specific user |
| `POST` | `/send/:id` | Send a message (text or image) |

---

## 🌐 Real-time Events (Socket.IO)

| Event | Direction | Description |
|---|---|---|
| `connection` | Client → Server | User connects and registers socket |
| `disconnect` | Client → Server | User disconnects, removed from online map |
| `getOnlineUsers` | Server → All Clients | Broadcasts updated list of online user IDs |
| `newMessage` | Server → Receiver | Delivers a new message to a specific user |

---

## 📄 License

This project is licensed under the **ISC License**.

---

> Built with ❤️ by [Vardaan Singhal](https://github.com/vardaansinghal17)
