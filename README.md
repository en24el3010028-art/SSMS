# Student Skill Management System (SSMS) — MERN

## Deployment configuration

### Render backend
GITHUB REPO: https://github.com/en24el3010028-art/SSMS
- Branch: `main`
- Root Directory: `server`
- Build Command: `npm install`
- Start Command: `npm start`

Render environment variables:
- `MONGO_URI`: MongoDB Atlas connection string
- `JWT_SECRET`: long random secret
- `CLIENT_URL`: exact Vercel production origin, e.g. `https://your-app.vercel.app`
- `NODE_ENV`: `production`

The server exposes `/` and `/api/health`. Both include a build identifier so you can verify which code is deployed.

### Vercel frontend
- Root Directory: `client`
- Framework: Vite
- Build Command: `npm run build`
- Output Directory: `dist`

Vercel environment variable:
`VITE_API_URL=https://YOUR-RENDER-SERVICE.onrender.com/api`

The value includes `/api`; the frontend does not append another `/api`.

After changing environment variables, redeploy Vercel.

## Local development
Backend:
```powershell
cd server
npm install
Copy-Item .env.example .env
# Edit server/.env
npm run seed
npm run dev
```
Frontend, in another terminal:
```powershell
cd client
npm install
npm run dev
```

Demo accounts (all passwords `Demo@123`):
- student@ssms.demo
- faculty@ssms.demo
- placement@ssms.demo
- recruiter@ssms.demo
- admin@ssms.demo

Run `npm run seed` against the same MongoDB database configured in Render to create demo accounts in production. Do not commit `.env`.
