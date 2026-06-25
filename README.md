# FIFA World Cup 2026 Infoscreen

Real-time World Cup group standings, schedule, and knockout bracket powered by ESPN data.

## Features

✅ **Two Pages:**
- **Groups** (`index.html`) — All 8 group tables (A-H) with live standings, calendar, and tickers
- **Bracket** (`bracket.html`) — Knockout rounds (Round 32 → Final) with live scores

✅ **Auto-Refresh:**
- **During games**: Every 30 seconds
- **No games**: Every 30 minutes
- Updates scores, standings, and bracket automatically

✅ **Live Data:**
- ESPN Soccer API integration
- Real-time match scores and status
- Adaptive UI (highlights live games, shows winners)

✅ **Responsive Design:**
- Optimized for desktop displays/infoscreens
- No page scrolling (fits viewport)
- FIFA 2026 official color scheme

## Files

```
├── index.html        (Groups stage page)
├── bracket.html      (Knockout bracket page)
└── README.md         (This file)
```

## Deployment to GitHub Pages

### Option 1: New Repository (Simple)

1. Create a new GitHub repo named `wc26-infoscreen`
2. Clone it locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/wc26-infoscreen.git
   cd wc26-infoscreen
   ```
3. Copy `index.html`, `bracket.html`, and `README.md` into the folder
4. Push to GitHub:
   ```bash
   git add .
   git commit -m "Initial FIFA WC26 infoscreen"
   git push origin main
   ```
5. In GitHub repo settings → Pages → select "Deploy from a branch" → main branch → root folder
6. Site goes live at `https://YOUR_USERNAME.github.io/wc26-infoscreen`

### Option 2: User/Organization Pages

If you want it at `https://YOUR_USERNAME.github.io` directly:

1. Create a repo named `YOUR_USERNAME.github.io`
2. Add the files to the root
3. Push and it's live immediately

## Customization

### Change Colors
Edit the CSS variables in the `<style>` section:
```css
:root {
  --gold: #FFD700;           /* FIFA gold */
  --live: #E31937;           /* Live match red */
  --bg: #07101f;             /* Dark background */
  --green: #00c97a;          /* Winner green */
}
```

### Change Refresh Rate
Search for the refresh intervals in the `<script>`:
```javascript
return isLive ? 30000 : 30 * 60 * 1000;  // 30s live, 30m idle
```

### Add More Teams
Update the `EMOJIS` object with country codes and flags (used for Real-time matching)

## Known Limitations

- Bracket matches are templates (derive winners from group stage once matches complete)
- ESPN API structure may change — monitor for breaking changes
- No local caching of historical data
- No offline mode

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (but optimized for desktop/infoscreen displays)

## Updates

Last updated: June 24, 2026

---

**Questions?** Check the ESPN API docs at `https://site.api.espn.com/`
