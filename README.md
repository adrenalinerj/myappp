# Full Deployment Guide: React Frontend + Express Backend (Glitch + Netlify)

This guide will walk you through deploying a React frontend (on **Netlify**) and an Express backend (on **Glitch**) using a single GitHub repository.

---
## Project Structure

Make sure your project is structured like this:

```
project-root/
├── client/         # React frontend
│   ├── package.json
│   └── ...
├── api-server/     # Express backend
│   ├── server.js
│   └── package.json
```

---
## 🌐 Deploying Express Backend on Glitch (Free)

###  Step 1: Prepare your backend
- Move `server.js` and `package.json` from `api-server/` to a separate folder or directly into a GitHub repo
- Make sure `package.json` has:

```json
"scripts": {
  "start": "node server.js"
}
```

###  Step 2: Push to GitHub
- Create a GitHub repo with only the `api-server` content
- Push your backend code

###  Step 3: Import to Glitch
1. Go to [https://glitch.com](https://glitch.com)
2. Sign in and click **"New Project > Import from GitHub"**
3. Paste your GitHub repo URL
4. After it imports, it will auto-deploy

###  Step 4: Check API URL
Your API will be available at:
```
https://your-project-name.glitch.me/api/tasks
```

---

##  Backend Configuration (CORS)
In your `server.js`, add:

```js
const cors = require('cors');
app.use(cors()); // Or restrict to Netlify domain
```

---
##  Final Checklist

- [x] Glitch backend is live and accessible
- [x] CORS is enabled on backend
- [x] React app is deployed on Netlify
- [x] API requests use the Glitch URL correctly

---

##  Test
- Open Netlify site → Try adding/deleting tasks
- Open Dev Tools → No CORS or network errors
- Check: `https://your-project.glitch.me/api/tasks` works in browser

---

##  Done!
