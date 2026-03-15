# 🎲 Loto Online

A real-time, multiplayer Vietnamese Bingo (Lô Tô) game playable on any device. Players join a room with a code, receive randomized tickets, and compete to complete a row first — all synchronized live across all screens.

**Live App:** [http://loto-online81.surge.sh/](http://loto-online81.surge.sh/)

---

## 📖 About

Lô Tô is a beloved Vietnamese party game similar to Bingo. **Loto Online** brings this experience to the web, allowing any group to play together remotely or in-person using their own smartphones — no installation needed. The Host controls the game flow from a dedicated dashboard, while Players get their own interactive ticket screens.

## ✨ Features

### 🏠 For Players
- **Join by Room Code** — Enter a room code to instantly receive a randomized Lô Tô ticket.
- **Interactive Ticket** — Tap numbers on your ticket to mark them as called.
- **Auto-Mark (Tự Động Dò)** — One-tap to automatically mark all numbers already drawn (30-second cooldown to keep it fair).
- **Bingo! Declaration** — Tap "Bingo!" when you complete a row to claim your win.
- **Player Reconnect** — Auto-saves game state to session storage; refresh the page and pick up right where you left off with automatic retry.

### 🎛️ For the Host
- **Room Management** — Create rooms and kick off games with a unique shareable code.
- **Number Drawing** — Draw numbers with configurable timing between each draw.
- **View All Tickets** — Inspect every player's ticket in real-time.
- **Near-Win Highlight** — Numbers close to completing a row flash yellow to build tension.
- **Mid-Game Protection** — New players are automatically blocked from joining once a game is in progress.

### 🎉 Game Experience
- **Confetti Celebration** — A full-screen confetti animation fires when a winner is declared.
- **Simultaneous Bingo** — A 5-second window allows multiple players to claim Bingo at the same time.
- **Reconnection Banner** — Displays a "Reconnecting..." overlay during connection recovery.

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React 19, TypeScript, Vite |
| **Styling** | Tailwind CSS v3 |
| **Real-time** | Supabase (WebSocket / Realtime) |
| **Routing** | React Router v7 |
| **Animations** | canvas-confetti |
| **Backend (Server)** | Node.js, Socket.io, Firebase |
| **Containerization** | Docker (multi-stage build) |
| **Deployment** | Firebase Hosting |

## 🏗️ Project Structure

```
loto-game/
├── client/                 # Frontend application (React + TypeScript + Vite)
│   ├── src/
│   │   ├── pages/          # Route-level page components (Home, Player, Host)
│   │   ├── components/     # Reusable UI components
│   │   ├── hooks/          # Custom React hooks (game state, socket, etc.)
│   │   ├── lib/            # Supabase client and API helpers
│   │   ├── utils/          # Utility functions (ticket generation, etc.)
│   │   ├── data/           # Static data (number sets, configs)
│   │   └── types.ts        # Shared TypeScript types
│   └── package.json
├── server_backup/          # Node.js/Socket.io server reference implementation
│   ├── gameManager.js      # Core game state machine
│   ├── lotoController.js   # Game logic & number generation
│   └── index.js            # Server entry point
├── Dockerfile              # Multi-stage Docker build (client + server)
├── firebase.json           # Firebase Hosting configuration
└── .firebaserc             # Firebase project alias
```

## 🚀 Getting Started (Local Development)

### Prerequisites
- Node.js 18+
- A [Supabase](https://supabase.com/) account and project

### Client Setup

1. Clone the repo and navigate to the client:
   ```bash
   git clone https://github.com/dangochinh/loto-online.git
   cd loto-online/client
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the `client/` folder:
   ```env
   VITE_SUPABASE_URL=https://your-project.supabase.co
   VITE_SUPABASE_ANON_KEY=your_anon_key
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

5. Open [http://localhost:5173](http://localhost:5173) in your browser.

### Docker (Full Stack)

To run the full application (client + server) in a container:

```bash
docker build -t loto-online .
docker run -p 8080:8080 loto-online
```

## 📋 Release History

See [RELEASE_NOTES.md](client/RELEASE_NOTES.md) for full version history.

| Version | Highlights |
|---|---|
| **v1.4.0** | Player Reconnect, Near-Win Highlight, SEO optimization |
| **v1.3.0** | Mid-Game Protection, Simultaneous Bingo support |
| **v1.2.0** | Winner Confetti, Auto-Mark, Host ticket viewer |

## 👤 Author

**Đặng Ngọc Chính**
- Portfolio: [dangochinh.github.io](https://dangochinh.github.io/)
- GitHub: [@dangochinh](https://github.com/dangochinh)
