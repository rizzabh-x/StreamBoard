# StreamBoard


A collaborative, real-time whiteboard where users can seamlessly draw and ideate together. It provides a platform for multiple users to enter a room, share a unique room ID, and collaborate on visual content simultaneously with integrated chat functionality.

## 🔮 Features

- 🎨 **Real-time Collaborative Drawing:** Multiple users can draw simultaneously on the same canvas
- 🚀 **Unique Room Generation:** Create and join rooms with unique room IDs for collaboration
- ✏️ **Comprehensive Drawing Tools:** Pen, pencil, eraser, shapes, text, and more
- 🎨 **Color Palette:** Wide range of colors and custom color picker
- 📏 **Adjustable Brush Sizes:** Customize stroke width for different drawing needs
- 💬 **Integrated Real-time Chat:** Communicate with collaborators while drawing
- 👥 **User Presence Indicators:** See who's online and actively drawing
- 📣 **Join/Leave Notifications:** Real-time notifications when users enter or exit rooms
- 💾 **Canvas Export:** Save your collaborative artwork as image files
- 🔄 **Undo/Redo Functionality:** Easily revert or restore drawing actions
- 🖱️ **Multi-cursor Support:** See where other users are drawing in real-time
- 📱 **Responsive Design:** Works seamlessly across desktop and mobile devices
- 🌓 **Theme Support:** Light and dark mode options for comfortable drawing
- 🔐 **Room Privacy:** Secure room access with unique identifiers
- ⚡ **Lightning Fast Sync:** Instant synchronization of all drawing actions
- 📊 **Canvas Controls:** Zoom, pan, and navigate large canvases easily

## 💻 Tech Stack

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![JavaScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=for-the-badge&logo=react-router&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![NodeJS](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![ExpressJS](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)

![Socket io](https://img.shields.io/badge/Socket.io-ffffff?style=for-the-badge)
![Git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

## ⚙️ Installation

1. **Fork this repository:** Click the Fork button located in the top-right corner of this page.
2. **Clone the repository:**
   ```bash
   git clone https://github.com/rizzabh-x/StreamBoard.git
   ```
3. **Set up the environment:**
   Create `.env` files in both client and server directories:

   Frontend (.env):
   ```bash
   VITE_BACKEND_URL=http://localhost:3000
   VITE_APP_NAME=StreamBoard
   ```

   Backend (.env):
   ```bash
   PORT=3000
   CORS_ORIGIN=http://localhost:5173
   ```

4. **Install dependencies:**
   Navigate to both directories and install dependencies:
   ```bash
   # Install client dependencies
   cd client
   npm install

   # Install server dependencies
   cd ../server
   npm install
   ```

5. **Start the development servers:**
   
   Open two terminal windows/tabs:
   
   **Terminal 1 (Backend):**
   ```bash
   cd server
   npm run dev
   ```
   
   **Terminal 2 (Frontend):**
   ```bash
   cd client
   npm run dev
   ```

6. **Access the application:**
   Open your browser and navigate to:
   ```
   http://localhost:5173/
   ```


## 🎨 Usage Guide

### Creating a Room
1. Visit the homepage
2. Click "Create Room" to generate a unique room ID
3. Share the room ID with collaborators
4. Start drawing together in real-time!

### Joining a Room
1. Enter the room ID provided by the room creator
2. Click "Join Room"
3. You'll be connected to the collaborative whiteboard instantly

### Drawing Tools
- **Pen Tool:** Free-hand drawing with customizable colors and sizes
- **Shape Tools:** Draw rectangles, circles, lines, and arrows
- **Text Tool:** Add text annotations to your drawings
- **Eraser:** Remove unwanted elements from the canvas
- **Color Picker:** Choose from preset colors or create custom colors
- **Brush Size:** Adjust stroke width for different drawing needs

### Chat Feature
- Use the integrated chat panel to communicate with collaborators
- Send messages while drawing without interrupting the workflow
- See typing indicators when others are composing messages

## 📱 API Documentation

### Socket Events

#### Client to Server Events
```javascript
// Join a room
socket.emit('userJoinedRoom', { 
  name, 
  roomId, 
  userId, 
  host, 
  presenter 
});

// Send drawing data - Pencil
socket.emit('drawPencil', { path, strokeColor, roomId });

// Send drawing data - Line
socket.emit('drawLine', { path, strokeColor, roomId });

// Send drawing data - Rectangle
socket.emit('drawRect', { path, strokeColor, roomId });

// Send eraser data
socket.emit('erase', { path, roomId });

// Send chat message
socket.emit('message', { message, roomId });
```

#### Server to Client Events
```javascript
// User joined notification
socket.on('userIsJoined', ({ users }) => { ... });

// User joined room confirmation
socket.on('userJoinedRoom', ({ success, user }) => { ... });

// Receive pencil drawing data
socket.on('onDrawPencil', ({ path, strokeColor }) => { ... });

// Receive line drawing data
socket.on('onDrawLine', ({ x1, y1, x2, y2, strokeColor }) => { ... });

// Receive rectangle drawing data
socket.on('onDrawRect', ({ x1, y1, x2, y2, strokeColor }) => { ... });

// Receive eraser data
socket.on('onErase', ({ x1, y1, x2, y2 }) => { ... });

// Receive chat message
socket.on('onMessage', ({ message, name }) => { ... });

// User disconnected
socket.on('onDisconnect', ({ name, socketId }) => { ... });
```

## 🔮 Features for Next Release

- **Canvas Templates:** Pre-designed templates for different use cases (brainstorming, wireframing, etc.)
- **Advanced Shape Tools:** More geometric shapes and smart shape recognition
- **Layer Management:** Multiple layers for complex drawings
- **Canvas Versioning:** Save and restore different versions of the canvas
- **User Permissions:** Admin controls for room management
- **Voice Chat Integration:** Audio communication alongside drawing
- **Mobile App:** Native mobile applications for iOS and Android
- **Canvas Sharing:** Export and share canvases via social media platforms
- **Collaborative Cursors:** See real-time cursor positions of all users
- **Drawing History:** Timeline view of all drawing actions

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 🙏 Acknowledgments

Special thanks to:

- **Socket.IO** for enabling real-time communication:
  - [Socket.IO Repository](https://github.com/socketio/socket.io)
  - [Socket.IO Documentation](https://socket.io/docs/)

- **Canvas HTML5** for powerful drawing capabilities:
  - [Canvas API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)

### 🚀 Technical Expertise:

Frontend: React.js, TypeScript, Tailwind CSS, HTML5 Canvas, Next.js
Backend: Node.js, Express.js, Socket.io, RESTful APIs
Real-time Technologies: WebSockets, Real-time synchronization, Live collaboration
Tools & Platforms: Git, GitHub, Vercel, Docker, VS Code
LinkedIn: Connect with www.linkedin.com/in/tanishq-tyagi-1b5234289
<br><br/>
GitHub: Follow @tanishq-t
