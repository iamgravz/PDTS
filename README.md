# PUPOUS Requirement Monitoring System

This project is a web-based and tablet-ready records monitoring system for the PUP Open University System. It is used to log received admission requirements, monitor missing documents, generate tracking references, and maintain student notification records.

## Prerequisites

- Node.js LTS
- PostgreSQL
- VS Code or any code editor

## Local setup

1. Install dependencies:

```bash
npm install
```

2. Create a `.env` file in the project root. You may copy the values from `.env.windows.example` (desktop/Windows) or `.env.mobile.example` (Android/tablet).

3. Create or reset the PostgreSQL database (see `database/README.md` for full details):

```bash
createdb -U postgres pup_ous_pdts
psql -U postgres -d pup_ous_pdts -f database/schema/pup_database_schema.sql
psql -U postgres -d pup_ous_pdts -f database/seeds/default_data.sql
```

4. Run the system:

```bash
npm run dev
```

5. Open the browser:

```text
http://localhost:3000
```

## Default accounts

Passwords are stored as bcrypt hashes in the database — these are the plaintext values to log in with, not what's stored.

Head Admin:

```text
Username: admin001
Password: pupadmin
```

Registrar Officer:

```text
Username: officer001
Password: pupofficer
```

## Android tablet build

Build and sync the Android project using Capacitor:

```bash
npm run cap:add:android
npm run cap:sync:android
npm run cap:open:android
```

For Android tablets, set `VITE_API_BASE_URL` in `.env.mobile` to the deployed backend URL or to the local network IP address of the computer running the server.
