# 3D Space Shooter

A thrilling 3D space shooter game built with Three.js featuring epic boss battles across 5 waves of increasingly challenging enemies.

![Game Preview](https://img.shields.io/badge/Game-3D%20Space%20Shooter-blue)
![Technology](https://img.shields.io/badge/Tech-Three.js-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## 🎮 Game Overview

**3D Space Shooter** is an action-packed browser-based game where players navigate through space, battling waves of alien enemies and facing terrifying boss monsters. The game features:

- **5 Unique Waves** with progressively harder enemies
- **5 Epic Boss Battles** featuring grotesque, organic alien creatures
- **3D Movement System** - Full control in X, Y, and Z axes
- **Power-up System** - Health recovery items and bomb power-ups
- **Dynamic Boss AI** - Bosses move unpredictably through 3D space, including retreat and charge patterns
- **Special Attacks** - Each boss has unique special attacks using their body parts (tentacles, claws, etc.)

## 👾 Boss Monsters

| Wave | Boss Name | Description |
|------|-----------|-------------|
| 1 | **Abyssal Eye Demon** | A massive flesh mass with countless eyes and 16 organic tentacles |
| 2 | **Twin-Headed Serpent Dragon** | A 30-segment serpentine body with two dragon heads |
| 3 | **Abyssal Kraken** | 8 main tentacles + 16 auxiliary tentacles with bioluminescent organs |
| 4 | **Insect Emperor** | A chitinous nightmare with 9 segments, scythe jaws, and venomous stinger |
| 5 | **Final Boss: Emperor of Doom** | Multi-dimensional entity with void tentacles, evil eyes, magic circles, and doom wings |

## 🏗️ Architecture

### Technology Stack
- **Three.js r128** - 3D rendering engine
- **Vanilla JavaScript** - Game logic and controls
- **HTML5/CSS3** - UI and styling

### File Structure
```
3D_space_shooter/
├── index.html      # Main game file (contains all HTML, CSS, and JavaScript)
└── README.md       # This file
```

### Key Components

```
Game Architecture:
├── Rendering Layer (Three.js)
│   ├── Scene, Camera, Renderer
│   ├── Lighting (Ambient + Directional)
│   └── Post-processing effects
│
├── Game Objects
│   ├── Player (spaceship with shields)
│   ├── Enemies (BasicAlien, FastAlien, TankAlien, SwarmAlien)
│   ├── Bosses (BossAlien1-5)
│   ├── Projectiles (player and enemy)
│   └── Items (HealthItem, BombItem)
│
├── Game Systems
│   ├── Collision Detection
│   ├── Wave Management
│   ├── Score System
│   └── Health/Shield System
│
└── UI Layer
    ├── HUD (Health, Shield, Score, Wave)
    ├── Menu Screens
    └── Game Over/Victory Screens
```

## 🎯 Controls

| Key | Action |
|-----|--------|
| **W / ↑** | Move Up |
| **S / ↓** | Move Down |
| **A / ←** | Move Left |
| **D / →** | Move Right |
| **Q** | Move Forward (into screen) |
| **E** | Move Backward (out of screen) |
| **Space** | Fire Weapon |
| **B** | Use Bomb (screen-clearing attack) |

## 🚀 Deployment

### Option 1: GitHub Pages (Recommended for Static Hosting)

1. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Navigate to **Settings** → **Pages**
   - Under "Source", select **main** branch
   - Click **Save**

2. **Access your game:**
   - Your game will be available at: `https://[username].github.io/3D_space_shooter/`
   - It may take a few minutes for the deployment to complete

### Option 2: Local Development Server

```bash
# Using Python 3
cd 3D_space_shooter
python3 -m http.server 8080

# Using Node.js (http-server)
npx http-server -p 8080

# Using PHP
php -S localhost:8080
```

Then open `http://localhost:8080` in your browser.

### Option 3: Cloud Server Deployment

#### AWS S3 + CloudFront

1. **Create S3 Bucket:**
   ```bash
   aws s3 mb s3://your-game-bucket
   aws s3 website s3://your-game-bucket --index-document index.html
   ```

2. **Upload Files:**
   ```bash
   aws s3 sync . s3://your-game-bucket --exclude ".git/*"
   ```

3. **Set Bucket Policy for Public Access:**
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::your-game-bucket/*"
       }
     ]
   }
   ```

4. **Optional: Set up CloudFront for CDN**

#### Google Cloud Storage

1. **Create Bucket:**
   ```bash
   gsutil mb gs://your-game-bucket
   ```

2. **Upload and Make Public:**
   ```bash
   gsutil cp -r . gs://your-game-bucket
   gsutil iam ch allUsers:objectViewer gs://your-game-bucket
   ```

3. **Enable Website Hosting:**
   ```bash
   gsutil web set -m index.html gs://your-game-bucket
   ```

#### Netlify

1. **Drag and Drop:** Simply drag your project folder to [Netlify Drop](https://app.netlify.com/drop)

2. **Or use CLI:**
   ```bash
   npm install -g netlify-cli
   netlify deploy --prod --dir=.
   ```

#### Vercel

```bash
npm install -g vercel
vercel --prod
```

#### Firebase Hosting

```bash
npm install -g firebase-tools
firebase init hosting
firebase deploy
```

## 🎨 Game Features

### Visual Effects
- Dynamic particle explosions
- Glowing energy effects
- Pulsating boss animations
- Dimensional rift background (Wave 5)

### Boss AI Behaviors
- **Multi-phase movement patterns** - 6-8 different movement phases per boss
- **Retreat mechanics** - Bosses flee to far distances then return aggressively
- **Special attacks** - Tentacle sweeps, poison breath, dimensional beams
- **Rage mode** - Bosses become more aggressive at low health

### Game Balance
- Progressive difficulty scaling
- HP recovery items drop from enemies
- Bomb power-ups for emergency situations
- Shield regeneration system

## 🔧 Configuration

Key game parameters can be modified in the JavaScript code:

```javascript
// Player settings
this.maxHealth = 100;
this.maxShield = 100;
this.speed = 40;

// Boss HP values
BossAlien1: 21600 HP
BossAlien2: 32400 HP
BossAlien3: 32400 HP
BossAlien4: 45000 HP
BossAlien5: 72000 HP

// Wave configuration
totalWaves: 5
enemiesPerWave: varies by wave
```

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📧 Contact

For questions or feedback, please open an issue on GitHub.

---

**Enjoy the game and good luck defeating the Emperor of Doom! 🚀👾**
