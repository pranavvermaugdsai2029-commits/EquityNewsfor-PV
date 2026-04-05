# EquityLens Terminal

A real-time equity-focused news terminal powered by Google News RSS.

## Setup (2 minutes)

### 1. Install dependencies
```bash
npm install
```

### 2. Start the backend
```bash
node server.js
```
You'll see:
```
✅ EquityLens backend running at http://localhost:3001
```

### 3. Open the app
Open your browser and go to:
```
http://localhost:3001
```

That's it. The frontend is served by the same Express server.

---

## How it works

- **Backend** (`server.js`): Express server that fetches Google News RSS feeds
  and parses the XML. Runs on port 3001.
- **Frontend** (`public/index.html`): Single HTML file, no build step needed.
  Talks to the backend at `localhost:3001/api/news`.

## API

```
GET /api/news?section=Headlines&mode=IND
GET /api/news?section=Banking&mode=INT
GET /api/news?q=ICICI+Bank+results&mode=IND   ← custom search
```

## Adding more section queries

Edit the `SECTION_QUERIES` object in `server.js` to tune what each sidebar
section fetches. The format is plain English — Google News will handle the rest.

## Customising regions

- `mode=IND` → India (`hl=en-IN&gl=IN&ceid=IN:en`)
- `mode=INT` → Global/US (`hl=en-US&gl=US&ceid=US:en`)
