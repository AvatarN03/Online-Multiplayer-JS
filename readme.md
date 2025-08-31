# Online-Multiplayer-JS

A real-time online multiplayer JavaScript game built with HTML5 Canvas, Socket.io, and Node.js. This project demonstrates multiplayer game mechanics including player movement, real-time synchronization, and client-server architecture.

## 🎮 About

This project is based on the Chris Courses Online Multiplayer Game Tutorial and serves as both a learning resource and a foundation for building multiplayer browser games. The game features real-time player interactions, smooth movement mechanics, and efficient client-server communication.

## 🚀 Features

- **Real-time Multiplayer**: Multiple players can join and interact simultaneously
- **Smooth Movement**: Client-side prediction with server reconciliation
- **Player Synchronization**: Real-time position updates across all clients
- **HTML5 Canvas Rendering**: Hardware-accelerated 2D graphics
- **WebSocket Communication**: Low-latency real-time networking via Socket.io
- **Cross-platform Compatibility**: Works on desktop and mobile browsers
- **Responsive Design**: Adapts to different screen sizes
- **Player Authentication**: Basic player identification system
- **Connection Management**: Handles player join/leave events gracefully

## 🛠️ Tech Stack

### Frontend
- **HTML5 Canvas** - Game rendering and graphics
- **Vanilla JavaScript** - Game logic and client-side mechanics
- **Socket.io Client** - Real-time communication
- **CSS3** - Styling and responsive design

### Backend
- **Node.js** - Server runtime
- **Express.js** - Web server framework
- **Socket.io** - WebSocket server for real-time communication
- **UUID** - Unique player identification

## 📋 Prerequisites

- Node.js (v14.0 or higher)
- npm or yarn
- Modern web browser (Chrome, Firefox, Safari, Edge)

## 🔧 Installation & Setup

### Quick Start (Single Player Mode)

1. **Clone the repository**
   ```bash
   git clone https://github.com/AvatarN03/Online-Multiplayer-JS.git
   cd Online-Multiplayer-JS
   ```

2. **Open the single-player version**
   
   Simply double-click `index.html` or open it in your web browser to see the base single-player game.

### Full Multiplayer Setup

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Start the development server**
   ```bash
   npm start
   ```

3. **Open the game**
   
   Navigate to `http://localhost:3000` in your web browser.

4. **Test multiplayer**
   
   Open multiple browser tabs or windows to test the multiplayer functionality.

## 📁 Project Structure

```
Online-Multiplayer-JS/
├── public/                 # Client-side files
│   ├── index.html         # Main HTML file
│   ├── css/
│   │   └── style.css      # Game styling
│   ├── js/
│   │   ├── game.js        # Main game logic
│   │   ├── player.js      # Player class
│   │   ├── input.js       # Input handling
│   │   ├── canvas.js      # Canvas utilities
│   │   └── socket.js      # Socket.io client
│   └── assets/            # Game assets (images, sounds)
├── server/                # Server-side files
│   ├── server.js          # Main server file
│   ├── game/
│   │   ├── gameLoop.js    # Server game loop
│   │   ├── player.js      # Server player logic
│   │   └── collision.js   # Collision detection
│   └── socket/
│       └── socketHandler.js # Socket event handlers
├── shared/                # Shared utilities
│   ├── constants.js       # Game constants
│   └── utils.js          # Utility functions
├── package.json
├── README.md
└── .gitignore
```

## 🎮 Game Controls

- **Arrow Keys** or **WASD** - Move player
- **Mouse** - Aim (if applicable)
- **Space** - Action/Shoot (if applicable)
- **Enter** - Chat (if implemented)

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the root directory:

```env
PORT=3000
NODE_ENV=development
MAX_PLAYERS=50
TICK_RATE=60
```

### Game Constants

Modify `shared/constants.js` to adjust game parameters:

```javascript
module.exports = {
  CANVAS_WIDTH: 800,
  CANVAS_HEIGHT: 600,
  PLAYER_SPEED: 5,
  MAX_PLAYERS: 10,
  TICK_RATE: 60
};
```

## 🌐 Socket.io Events

### Client to Server
- `playerJoin` - Player joins the game
- `playerMove` - Player movement input
- `playerAction` - Player actions (shoot, etc.)
- `disconnect` - Player leaves the game

### Server to Client
- `gameState` - Current game state update
- `playerJoined` - New player joined notification
- `playerLeft` - Player left notification
- `playerMoved` - Player position update

## 🎯 Game Architecture

### Client-Side Prediction
The game implements client-side prediction to ensure smooth gameplay:
- Players see their actions immediately
- Server validates and corrects positions if needed
- Interpolation smooths out network jitter

### Server Authority
- Server maintains the authoritative game state
- Validates all player inputs
- Broadcasts updates to all clients
- Handles collision detection and game rules

## 🚀 Deployment

### Local Deployment
```bash
npm run build
npm start
```

### Heroku Deployment
```bash
# Install Heroku CLI
npm install -g heroku

# Login and create app
heroku login
heroku create your-game-name

# Deploy
git push heroku main
```

### Docker Deployment
```dockerfile
FROM node:16-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

## 🧪 Development

### Adding New Features

1. **Client-side changes**: Modify files in `public/js/`
2. **Server-side changes**: Modify files in `server/`
3. **Shared logic**: Use `shared/` for code used by both client and server

### Testing Multiplayer Locally

- Open multiple browser tabs/windows
- Use different browsers
- Test with browser dev tools network throttling
- Use incognito/private browsing windows

## 📚 Learning Resources

- [Original Tutorial Video](https://www.youtube.com/watch?v=Wcvqnx14cZA)
- [HTML5 Canvas API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [Socket.io Documentation](https://socket.io/docs/v4/)
- [Chris Courses Website](https://chriscourses.com/)

## 🎨 Customization Ideas

### Visual Enhancements
- Add particle effects
- Implement sprite animations
- Create custom player skins
- Add background graphics and tiles

### Gameplay Features
- Power-ups and collectibles
- Different game modes (team battles, capture the flag)
- Leaderboards and scoring system
- Chat system
- Spectator mode

### Technical Improvements
- Player interpolation and lag compensation
- Authoritative physics simulation
- Anti-cheat measures
- Player matchmaking
- Database integration for persistent data

## 🐛 Common Issues & Troubleshooting

### Port Already in Use
```bash
Error: listen EADDRINUSE :::3000
```
**Solution**: Change the port in your `.env` file or kill the process using port 3000.

### Canvas Not Rendering
- Check browser console for JavaScript errors
- Ensure HTML5 Canvas is supported
- Verify file paths are correct

### Multiplayer Not Working
- Check if Socket.io server is running
- Verify firewall settings
- Test with localhost first before deploying

### Performance Issues
- Monitor browser dev tools performance tab
- Reduce game tick rate if needed
- Optimize canvas rendering calls
- Use requestAnimationFrame properly

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test multiplayer functionality
5. Commit your changes (`git commit -m 'Add some amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

### Development Guidelines
- Follow existing code style and structure
- Test both single-player and multiplayer modes
- Comment complex game logic
- Update README if adding new features

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- **[Chris Courses](https://chriscourses.com/)** - Original tutorial and inspiration
- **Socket.io Team** - Excellent real-time communication library
- **HTML5 Canvas Community** - Extensive documentation and examples
- **Open Source Contributors** - Everyone who has contributed to making web game development accessible

## 📞 Support

If you encounter any issues:

1. Check the [Issues](https://github.com/AvatarN03/Online-Multiplayer-JS/issues) page
2. Review the troubleshooting section above
3. Create a new issue with detailed information
4. Join the discussion in the original tutorial comments

---

**Ready to build your own multiplayer game? Fork this repo and start coding!**

*Made with ❤️ by [AvatarN03](https://github.com/AvatarN03) | Based on Chris Courses Tutorial*
