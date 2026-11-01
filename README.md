# Silence Nodes

Node.js + Express hosting website with 30 protected content pages.

## Run locally
1. Install Node.js 20 or newer.
2. In this folder run `npm install`.
3. Copy `.env.example` to `.env` and set a long random `SESSION_SECRET`.
4. Run `npm start`.
5. Open `http://localhost:3000/register` to create your first account, then sign in at `/login`.

The root URL redirects visitors to login. All 30 content pages require an authenticated session. Passwords are hashed with bcryptjs and users are stored in SQLite.

## Important before production
- Set a strong `SESSION_SECRET` in the hosting environment.
- Use HTTPS and `NODE_ENV=production`.
- For multiple server instances, replace the default in-memory Express session store with a shared persistent session store.
- Configure backups for `silence-nodes.db`.
- Add CSRF protection, email verification, password reset, billing and a real client-area integration before accepting customers.
- Replace placeholder policies/contact details and verify all service claims/prices.
