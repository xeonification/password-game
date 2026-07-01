# 🔒 Password — party game

A real-time, multiplayer **Password** word-guessing game that runs entirely in the browser. Everyone plays on their own phone, there's **no sign-in and no accounts**, and there's **no server to run** — devices connect peer-to-peer over a free public broker.

👉 **[Play it here](https://YOUR-USERNAME.github.io/YOUR-REPO/)** *(replace with your Pages URL)*

## How to play

1. One person opens the link and taps **Host** — they become the game master and get a 4-letter room code.
2. Everyone else opens the same link, taps **Join**, and enters the code + their name.
3. The host taps **Shuffle into teams** (teams of 2). Rename teams or reshuffle if you like, then start.
4. Each round, one password is in play, worth **7 points**:
   - The active team's **clue-giver** sees the word on their phone and gives *single-word* clues out loud; their partner guesses.
   - The host buzzes **Correct** (that team scores the current value) or **Wrong / Pass** (the word moves to the next team and loses a point).
   - The word keeps bouncing between teams, dropping a point each pass, until someone gets it or it hits **0** (burned).
5. Highest score after all rounds wins. 🏆

## Features

- Everyone on their own screen — the secret word is sent **only** to the current clue-giver's device.
- Host controls: shuffle / reshuffle teams, editable team names, round settings (time, starting points, number of rounds), a custom word list, **cancel game**, **disqualify team** (points split among the rest), and **void round** for fouls.
- Confetti on a correct guess and a big red ✕ on a wrong guess/pass, on every screen.
- Screen stays awake during play; games survive an accidental refresh.

## Hosting it yourself

It's a single self-contained HTML file — host it anywhere static:

- **GitHub Pages:** put the file in your repo as `index.html`, then enable Pages (Settings → Pages → deploy from branch).
- Or drag it onto **Netlify Drop**, **Cloudflare Pages**, **Vercel**, or **itch.io**.

> ⚠️ It must be opened over **https** in a normal browser tab (not inside an editor preview), since it uses WebRTC.

## How it works

- **Preact/React UI** with everything precompiled into one HTML file (no build step needed to host).
- **[PeerJS](https://peerjs.com/)** for peer-to-peer WebRTC. The host is the authority; players connect directly to it. STUN + free public TURN relays are used for NAT traversal.

## Good to know

- Works best when everyone is on the **same Wi-Fi**. Very locked-down corporate/cellular networks can block peer connections.
- The **host's tab is the brain** — keep it open for the whole game; if it closes, the game pauses.
- Because there's no back-end, secrecy is trust-based for honest play.

---

Built for fun. 🎉
