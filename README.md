<div align="center">

# 🎮 PAC-MAN

### *A Classic Arcade Experience in Pure Java*

[![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.java.com/)
[![Swing](https://img.shields.io/badge/Java_Swing-007396?style=for-the-badge&logo=java&logoColor=white)](https://docs.oracle.com/javase/tutorial/uiswing/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

[Features](#-features) • [Screenshots](#-screenshots) • [Installation](#-installation) • [Controls](#-controls) • [Tech Stack](#-tech-stack)

---

</div>

## 🌟 Overview

Relive the golden age of arcade gaming with this faithful recreation of **Pac-Man** built entirely in Java! Navigate through the maze, collect all the dots, and outsmart four colorful ghosts in this nostalgic tribute to one of gaming's most iconic titles.

<div align="center">

### ⭐ *Waka Waka Your Way to Victory!* ⭐

</div>

---

## 📸 Screenshots

<div align="center">

### 🎯 Gameplay Action

<img src="https://github.com/user-attachments/assets/f90f1268-e504-40dd-b574-d37ca1b9477a" alt="Pac-Man Gameplay" width="45%"/> <img src="https://github.com/user-attachments/assets/320bc6b4-6d94-4030-a26f-43bbc8ce4349" alt="Pac-Man Maze" width="45%"/>

</div>

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🎮 **Gameplay**
- 👻 **Four Ghost Enemies** with unique AI behaviors
- 🍒 **Dot Collection System** with real-time scoring
- 🏆 **High Score Tracking** for competitive play
- ⚡ **Smooth Movement** with responsive controls

</td>
<td width="50%">

### 🛠️ **Technical**
- 🚧 **HashSet-Based Maze** for efficient collision detection
- 🎨 **Java Swing UI** with custom graphics
- ⌨️ **KeyListener Integration** for input handling
- 🔄 **Optimized Game Loop** for consistent performance

</td>
</tr>
</table>

---

## 🚀 Installation

### Prerequisites

```bash
☕ Java Development Kit (JDK) 8 or higher
```

### Quick Start

1️⃣ **Clone the repository**
```bash
git clone https://github.com/your-username/pacman-java-game.git
cd pacman-java-game
```

2️⃣ **Compile the game**
```bash
javac *.java
```

3️⃣ **Run and play!**
```bash
java PacManGame
```

---

## 🎮 Controls

<div align="center">

| Key | Action |
|:---:|:------:|
| <kbd>↑</kbd> | Move Up |
| <kbd>↓</kbd> | Move Down |
| <kbd>←</kbd> | Move Left |
| <kbd>→</kbd> | Move Right |
| <kbd>ESC</kbd> | Pause Game |
| <kbd>SPACE</kbd> | Restart |

</div>

---

## 🏗️ Tech Stack

<div align="center">

| Technology | Purpose |
|------------|---------|
| **Java Core** | Main programming language |
| **Java Swing** | UI framework (`JFrame`, `JPanel`) |
| **HashSet** | Wall and path management |
| **KeyListener** | Keyboard input handling |
| **2D Graphics** | Custom rendering engine |

</div>

---

## 🎯 Game Mechanics

### Ghost AI Behavior

```
👻 Blinky (Red)    → Aggressive chaser
👻 Pinky (Pink)    → Ambush strategist
👻 Inky (Cyan)     → Unpredictable flanker
👻 Clyde (Orange)  → Shy wanderer
```

### Scoring System

- 🔵 **Regular Dot**: 10 points
- 🔴 **Power Pellet**: 50 points
- 👻 **Ghost (vulnerable)**: 200 points
- 🍒 **Bonus Fruit**: 100+ points

---

## 📂 Project Structure

<div align="center">

### 🗺️ Navigate Through The Maze 🗺️

</div>

```
🎮 pacman-java-game/
│
├── ☕ GAME LOGIC
│   ├── App.class                  🔵 Compiled main application
│   ├── App.java                   🔵 Main entry point - Start here!
│   ├── PacManBlock.class          🔵 Compiled block class
│   ├── PacMan.class               🔵 Compiled PacMan class
│   └── PacMan.java                🔵 Player character logic
│
├── 👻 GHOST SQUAD
│   ├── blueGhost.png              💙 Inky - The Bashful One
│   ├── orangeGhost.png            🧡 Clyde - The Pokey One
│   ├── pinkGhost.png              💗 Pinky - The Speedy One
│   ├── redGhost.png               ❤️ Blinky - The Leader
│   └── scaredGhost.png            😱 Vulnerable Mode!
│
├── 🟡 PAC-MAN SPRITES
│   ├── pacmanDown.png             ⬇️ Waka waka downward
│   ├── pacmanRight.png            ➡️ Waka waka rightward
│   └── pacmanUp.png               ⬆️ Waka waka upward
│
├── 🍒 COLLECTIBLES & MAZE
│   ├── cherry.png                 🍒 Bonus fruit
│   ├── cherry2.png                🍒 Alternative cherry
│   ├── powerFood.png              ⚡ Power pellet - Ghost hunting time!
│   └── wall.png                   🧱 Maze wall tile
│
└── 📖 README.md                   📜 You are here! (READY PLAYER ONE)
```

<div align="center">

**🔵 = Dots to collect** • **👻 = Enemies to avoid** • **⚡ = Power-ups to grab**

</div>

---

## 🤝 Contributing

Contributions are what make the open-source community amazing! Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

---

## 🎖️ Acknowledgments

- Original Pac-Man concept by Namco
- Inspired by the classic arcade game from 1980
- Built with ☕ and nostalgia

---

<div align="center">

### 🌟 If you enjoyed this project, don't forget to give it a star! 🌟

**Made with 💛 by [Your Name]**

[⬆ Back to Top](#-pac-man)

</div>
