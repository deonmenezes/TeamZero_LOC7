# TeamZero LOC7

A Node.js/Express REST API backend built for a hackathon, providing user authentication (register/login) with JWT tokens, backed by both MongoDB and SQLite.

## Tech Stack

- **Runtime:** Node.js (ESM modules)
- **Framework:** Express 4
- **Databases:** MongoDB (via Mongoose), SQLite (via sqlite/sqlite3)
- **Auth:** bcrypt (password hashing), jsonwebtoken (JWT)
- **Other:** axios, cors

## Setup

```bash
npm install
```

Requires a running MongoDB instance at `mongodb://127.0.0.1:27017/hackathon` (default URI in `server.js`).

## Build / Run / Test

```bash
# Start the server (port 5000)
node server.js
```

No build step required. No tests are configured (`npm test` exits with an error by design).

## Project Structure

```
TeamZero_LOC7/
├── server.js          # Main Express server: routes, auth logic, DB connections
├── package.json       # Dependencies and scripts
├── package-lock.json
├── users.db           # SQLite database file (local)
├── download/          # Downloaded/extracted frontend or additional assets
└── teamzero_o1/       # Additional project files or frontend assets
```

## Architecture & Key Files

- `server.js` — Single-file backend. Defines Express app on port 5000, connects to MongoDB, defines `User` schema (user_name, email, password, role), and exposes auth endpoints.
- `users.db` — SQLite database; both MongoDB and SQLite appear to be in use simultaneously.

## Conventions & Notes for Agents

- The `SECRET_KEY` in `server.js` is hardcoded as `"supersecretkey"` — replace with an environment variable before any production or demo use.
- The MongoDB URI is also hardcoded; externalize it via `process.env.MONGO_URI`.
- The project uses ES modules (`"type": "module"` in package.json); use `import`/`export` syntax, not `require`.
- No linting or formatting config is present; match the existing code style.
- `node_modules/` is committed to the repo — do not delete it but prefer not adding more committed dependencies.
