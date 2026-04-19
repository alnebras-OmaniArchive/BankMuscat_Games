[README.md](https://github.com/user-attachments/files/26865589/README.md)
# Bank Muscat Jeopardy Games

Two standalone Jeopardy-style game boards built for Bank Muscat events. Each game is a single HTML file with no dependencies or build steps required.

---

## File Structure

```
jeopardy-games/
├── README.md
├── game1/
│   └── index.html          ← Jeopardy 1: Sport, Brand, Famous People, Culture, Food
└── game2/
    ├── index.html          ← Jeopardy 2: IT Acronyms, Money Bills, White & Red, Country Currency, IT Phrases
    └── images/
        ├── 1-rial.jpg
        ├── 5-rials.jpg
        ├── 200-baisa.jpg
        ├── 20-rials.jpg
        └── 50-rials.jpg
```

---

## Adding Images for Game 2 (Money Bills)

The Money Bills category in Game 2 shows a photo of the bill as the question, then reveals the denomination as the answer.

1. Add your bill images to the `game2/images/` folder
2. Name them exactly as follows:
   - `1-rial.jpg`
   - `5-rials.jpg`
   - `200-baisa.jpg`
   - `20-rials.jpg`
   - `50-rials.jpg`
3. If your images are `.png` or `.webp` instead of `.jpg`, open `game2/index.html` and find the Money Bills data array (look for `img:`) and update the extensions to match

---

## How to Play

- **Click** any tile to open the question
- **Press SPACE** (or click Reveal Answer) to show the answer as a red bar
- **Press ESC** (or click Close) to mark the tile as used and return to the board
- Used tiles turn dark red so you know they've been played

---

## Deploying to Vercel

Each game is deployed as a **separate Vercel project** from the same GitHub repository. Vercel's free Hobby plan supports unlimited projects, so both can be deployed for free.

### Step 1 — Push to GitHub

Create a new GitHub repository and push this entire folder to it:

```bash
git init
git add .
git commit -m "initial commit"
git remote add origin https://github.com/YOUR_USERNAME/jeopardy-games.git
git push -u origin main
```

### Step 2 — Deploy Game 1 on Vercel

1. Go to [vercel.com](https://vercel.com) and click **Add New Project**
2. Import your GitHub repository
3. Under **Root Directory**, click Edit and set it to `game1`
4. Leave all other settings as default
5. Click **Deploy**

Vercel will give you a live URL like `game1-abc123.vercel.app`

### Step 3 — Deploy Game 2 on Vercel

1. Go to [vercel.com](https://vercel.com) and click **Add New Project** again
2. Import the **same GitHub repository**
3. Under **Root Directory**, set it to `game2`
4. Leave all other settings as default
5. Click **Deploy**

Vercel will give you a second live URL like `game2-abc123.vercel.app`

> **Important for Game 2:** Make sure you have added your bill images to `game2/images/` and pushed them to GitHub **before** deploying. If you add images later, just push the changes to GitHub and Vercel will automatically redeploy.

### Step 4 — Custom Domains (Optional)

If you want cleaner URLs like `jeopardy1.yourdomain.com`:
1. Open the project in Vercel
2. Go to **Settings → Domains**
3. Add your custom domain and follow the DNS instructions

---

## Making Changes

Since both projects are connected to the same GitHub repo, any time you push a change Vercel will automatically redeploy the affected project. You don't need to do anything manually in Vercel after the initial setup.
