<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PAC-MAN Game - Java Edition</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: #000;
            color: #FFD700;
            font-family: 'Press Start 2P', cursive;
            padding: 20px;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: #0a0a1a;
            border: 5px solid #FFD700;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 0 50px rgba(255, 215, 0, 0.5),
                        inset 0 0 50px rgba(255, 215, 0, 0.1);
        }
        
        .header {
            text-align: center;
            margin-bottom: 40px;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { text-shadow: 0 0 20px #FFD700, 0 0 40px #FFD700; }
            50% { text-shadow: 0 0 30px #FFD700, 0 0 60px #FFD700, 0 0 80px #FFD700; }
        }
        
        .title {
            font-size: 3em;
            color: #FFD700;
            margin-bottom: 20px;
            letter-spacing: 5px;
        }
        
        .subtitle {
            font-size: 0.8em;
            color: #00FFFF;
            margin-bottom: 20px;
        }
        
        .badges {
            display: flex;
            gap: 10px;
            justify-content: center;
            flex-wrap: wrap;
            margin: 20px 0;
        }
        
        .badge {
            background: linear-gradient(135deg, #FFD700 0%, #FFA500 100%);
            color: #000;
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.5em;
            font-weight: bold;
            box-shadow: 0 4px 15px rgba(255, 215, 0, 0.4);
        }
        
        .game-border {
            border: 3px dashed #FFD700;
            padding: 30px;
            margin: 30px 0;
            border-radius: 15px;
            background: rgba(255, 215, 0, 0.05);
            position: relative;
        }
        
        .game-border::before {
            content: '🔵';
            position: absolute;
            top: -15px;
            left: 20px;
            font-size: 1.5em;
            animation: moveRight 3s linear infinite;
        }
        
        @keyframes moveRight {
            0% { left: 20px; }
            100% { left: calc(100% - 40px); }
        }
        
        h2 {
            color: #FFD700;
            font-size: 1.5em;
            margin: 30px 0 20px 0;
            text-align: center;
            text-shadow: 0 0 10px #FFD700;
        }
        
        h3 {
            color: #00FFFF;
            font-size: 1em;
            margin: 20px 0 10px 0;
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .feature-box {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            border: 3px solid #FFD700;
            border-radius: 15px;
            padding: 20px;
            transition: all 0.3s;
        }
        
        .feature-box:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
            border-color: #00FFFF;
        }
        
        .feature-icon {
            font-size: 2em;
            margin-bottom: 10px;
        }
        
        .feature-title {
            color: #FFD700;
            font-size: 0.8em;
            margin-bottom: 15px;
        }
        
        .feature-list {
            list-style: none;
            font-size: 0.5em;
            color: #fff;
            line-height: 2;
        }
        
        .feature-list li::before {
            content: '🔵 ';
            margin-right: 5px;
        }
        
        .controls-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }
        
        .control-key {
            background: #FFD700;
            color: #000;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            font-size: 0.6em;
            font-weight: bold;
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.4);
            transition: all 0.3s;
        }
        
        .control-key:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(255, 215, 0, 0.6);
        }
        
        .code-block {
            background: #000;
            border: 2px solid #FFD700;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            font-size: 0.5em;
            color: #00FF00;
            overflow-x: auto;
        }
        
        .ghost-squad {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }
        
        .ghost-card {
            background: rgba(0, 0, 0, 0.6);
            border: 3px solid;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            font-size: 0.5em;
            transition: all 0.3s;
        }
        
        .ghost-card:hover {
            transform: scale(1.1) rotate(5deg);
        }
        
        .ghost-red { border-color: #FF0000; }
        .ghost-pink { border-color: #FFB8FF; }
        .ghost-blue { border-color: #00FFFF; }
        .ghost-orange { border-color: #FFB851; }
        
        .score-table {
            background: rgba(0, 0, 0, 0.6);
            border: 3px solid #FFD700;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
        }
        
        .score-item {
            display: flex;
            justify-content: space-between;
            padding: 10px;
            border-bottom: 1px dashed #FFD700;
            font-size: 0.6em;
            color: #fff;
        }
        
        .score-item:last-child {
            border-bottom: none;
        }
        
        .file-tree {
            background: #000;
            border: 3px solid #FFD700;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            font-size: 0.5em;
            color: #00FF00;
            line-height: 2;
        }
        
        .file-section {
            margin: 15px 0;
            padding-left: 20px;
        }
        
        .section-title {
            color: #FFD700;
            font-size: 1.2em;
            margin: 10px 0;
        }
        
        .file-item {
            color: #00FFFF;
            padding: 5px 0;
        }
        
        .footer {
            text-align: center;
            margin-top: 40px;
            padding: 20px;
            border-top: 3px solid #FFD700;
            font-size: 0.6em;
            color: #FFD700;
        }
        
        .btn {
            background: linear-gradient(135deg, #FFD700 0%, #FFA500 100%);
            color: #000;
            padding: 15px 30px;
            border: none;
            border-radius: 10px;
            font-family: 'Press Start 2P', cursive;
            font-size: 0.6em;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.4);
            display: inline-block;
            margin: 10px;
            text-decoration: none;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255, 215, 0, 0.6);
        }
        
        .arcade-frame {
            border: 5px solid #FFD700;
            border-radius: 15px;
            padding: 20px;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            margin: 20px 0;
        }
        
        @media (max-width: 768px) {
            .title { font-size: 1.5em; }
            .container { padding: 20px; }
            .feature-box { font-size: 0.8em; }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="title">🟡 PAC-MAN 🟡</div>
            <div class="subtitle">A Classic Arcade Experience in Pure Java</div>
            <div class="badges">
                <span class="badge">☕ JAVA</span>
                <span class="badge">🎮 SWING</span>
                <span class="badge">👾 RETRO</span>
                <span class="badge">⚡ ARCADE</span>
            </div>
        </div>

        <div class="game-border">
            <h2>🌟 GAME OVERVIEW 🌟</h2>
            <p style="text-align: center; font-size: 0.6em; color: #fff; line-height: 1.8;">
                Relive the golden age of arcade gaming with this faithful recreation of PAC-MAN built entirely in Java! 
                Navigate through the maze, collect all the dots, and outsmart four colorful ghosts in this nostalgic 
                tribute to one of gaming's most iconic titles.
            </p>
        </div>

        <h2>✨ GAME FEATURES ✨</h2>
        <div class="features">
            <div class="feature-box">
                <div class="feature-icon">🎮</div>
                <div class="feature-title">GAMEPLAY</div>
                <ul class="feature-list">
                    <li>Four Ghost Enemies with unique AI</li>
                    <li>Dot Collection System</li>
                    <li>Real-time Score Tracking</li>
                    <li>Smooth Movement Controls</li>
                </ul>
            </div>
            <div class="feature-box">
                <div class="feature-icon">🛠️</div>
                <div class="feature-title">TECHNICAL</div>
                <ul class="feature-list">
                    <li>HashSet-Based Maze</li>
                    <li>Java Swing UI</li>
                    <li>KeyListener Integration</li>
                    <li>Optimized Game Loop</li>
                </ul>
            </div>
        </div>

        <div class="arcade-frame">
            <h2>🎮 CONTROLS 🎮</h2>
            <div class="controls-grid">
                <div class="control-key">⬆️ UP<br>Move Up</div>
                <div class="control-key">⬇️ DOWN<br>Move Down</div>
                <div class="control-key">⬅️ LEFT<br>Move Left</div>
                <div class="control-key">➡️ RIGHT<br>Move Right</div>
                <div class="control-key">ESC<br>Pause Game</div>
                <div class="control-key">SPACE<br>Restart</div>
            </div>
        </div>

        <h2>👻 GHOST SQUAD 👻</h2>
        <div class="ghost-squad">
            <div class="ghost-card ghost-red">
                <div style="font-size: 2em;">👻</div>
                <div style="color: #FF0000; margin: 10px 0;">BLINKY</div>
                <div style="color: #fff;">The Chaser</div>
            </div>
            <div class="ghost-card ghost-pink">
                <div style="font-size: 2em;">👻</div>
                <div style="color: #FFB8FF; margin: 10px 0;">PINKY</div>
                <div style="color: #fff;">The Ambusher</div>
            </div>
            <div class="ghost-card ghost-blue">
                <div style="font-size: 2em;">👻</div>
                <div style="color: #00FFFF; margin: 10px 0;">INKY</div>
                <div style="color: #fff;">The Flanker</div>
            </div>
            <div class="ghost-card ghost-orange">
                <div style="font-size: 2em;">👻</div>
                <div style="color: #FFB851; margin: 10px 0;">CLYDE</div>
                <div style="color: #fff;">The Wanderer</div>
            </div>
        </div>

        <div class="arcade-frame">
            <h2>🎯 SCORING SYSTEM 🎯</h2>
            <div class="score-table">
                <div class="score-item">
                    <span>🔵 Regular Dot</span>
                    <span style="color: #FFD700;">10 PTS</span>
                </div>
                <div class="score-item">
                    <span>⚡ Power Pellet</span>
                    <span style="color: #FFD700;">50 PTS</span>
                </div>
                <div class="score-item">
                    <span>👻 Ghost (Vulnerable)</span>
                    <span style="color: #FFD700;">200 PTS</span>
                </div>
                <div class="score-item">
                    <span>🍒 Bonus Fruit</span>
                    <span style="color: #FFD700;">100+ PTS</span>
                </div>
            </div>
        </div>

        <h2>🚀 INSTALLATION 🚀</h2>
        <div class="code-block">
<span style="color: #FFD700;"># Clone the repository</span>
git clone https://github.com/your-username/pacman-java-game.git
cd pacman-java-game

<span style="color: #FFD700;"># Compile the game</span>
javac *.java

<span style="color: #FFD700;"># Run and play!</span>
java App
        </div>

        <h2>📂 PROJECT STRUCTURE 📂</h2>
        <div class="file-tree">
<span style="color: #FFD700; font-size: 1.2em;">🎮 pacman-java-game/</span>
│
<div class="file-section">
<div class="section-title">☕ GAME LOGIC</div>
<div class="file-item">├── App.class          🔵 Compiled main application</div>
<div class="file-item">├── App.java           🔵 Main entry point</div>
<div class="file-item">├── PacManBlock.class  🔵 Compiled block class</div>
<div class="file-item">├── PacMan.class       🔵 Compiled PacMan class</div>
<div class="file-item">└── PacMan.java        🔵 Player character logic</div>
</div>

<div class="file-section">
<div class="section-title">👻 GHOST SQUAD</div>
<div class="file-item">├── blueGhost.png      💙 Inky - The Bashful One</div>
<div class="file-item">├── orangeGhost.png    🧡 Clyde - The Pokey One</div>
<div class="file-item">├── pinkGhost.png      💗 Pinky - The Speedy One</div>
<div class="file-item">├── redGhost.png       ❤️ Blinky - The Leader</div>
<div class="file-item">└── scaredGhost.png    😱 Vulnerable Mode!</div>
</div>

<div class="file-section">
<div class="section-title">🟡 PAC-MAN SPRITES</div>
<div class="file-item">├── pacmanDown.png     ⬇️ Waka waka downward</div>
<div class="file-item">├── pacmanRight.png    ➡️ Waka waka rightward</div>
<div class="file-item">└── pacmanUp.png       ⬆️ Waka waka upward</div>
</div>

<div class="file-section">
<div class="section-title">🍒 COLLECTIBLES & MAZE</div>
<div class="file-item">├── cherry.png         🍒 Bonus fruit</div>
<div class="file-item">├── cherry2.png        🍒 Alternative cherry</div>
<div class="file-item">├── powerFood.png      ⚡ Power pellet</div>
<div class="file-item">└── wall.png           🧱 Maze wall tile</div>
</div>

<span style="color: #00FFFF;">└── 📖 README.md</span>
        </div>

        <div class="footer">
            <h2>🌟 READY PLAYER ONE 🌟</h2>
            <p style="margin: 20px 0;">Made with 💛 and Nostalgia</p>
            <a href="#" class="btn">⭐ STAR THIS REPO</a>
            <a href="#" class="btn">🍴 FORK IT</a>
            <p style="margin-top: 30px; font-size: 0.8em;">
                🔵 = Dots to collect • 👻 = Enemies to avoid • ⚡ = Power-ups to grab
            </p>
        </div>
    </div>

    <script>
        // Add some interactive arcade effects
        document.querySelectorAll('.feature-box, .control-key, .ghost-card').forEach(element => {
            element.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.05)';
            });
            element.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1)';
            });
        });
    </script>
</body>
</html>
