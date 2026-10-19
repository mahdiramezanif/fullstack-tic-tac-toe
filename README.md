# Full-Stack Tic-Tac-Toe (React + FastAPI)

A two-player **Tic-Tac-Toe** project with a React frontend and a Python/FastAPI backend that stores player scores in PostgreSQL.

> **Status:** Coursework/prototype. The checked-in frontend dependencies and source code are not currently aligned; follow the known issues before attempting to run it.

## Features
- Two-player 3×3 Tic-Tac-Toe board
- Turn switching, winner checks, and draw detection
- Home, login, game, and scores pages
- API routes for creating players, updating scores, listing players, and showing a top-10 leaderboard

## Stack
- **Frontend:** React, Vite, Axios, Bootstrap, React Router
- **Backend:** Python, FastAPI, SQLAlchemy
- **Database:** PostgreSQL

## Structure

```text
frontend/    # React app and Vite configuration
backend/     # FastAPI app in main.py
```

## Development setup (requires fixes)

**Frontend:**

```bash
cd frontend
npm install
npm run dev
```

**Backend:** Set up Python dependencies (`fastapi`, `uvicorn`, `sqlalchemy`, `psycopg2-binary`) and a local PostgreSQL database, then from `backend/` run:

```bash
uvicorn main:app --reload --port 8000
```

API documentation: http://localhost:8000/docs.

## Known issues
1. The frontend uses `Routes` and `useNavigate` (React Router v6+ API), but `package.json` declares `react-router-dom` v5.2. Update the dependency and test the routes.
2. `GamePage.jsx` imports `./GamePage.css`, which is not present in the repository tree. Supply the stylesheet or remove the import.
3. The backend includes a **hard-coded PostgreSQL password**. Rotate it if real and load the connection URL from the environment instead.
4. Database sessions are not consistently closed, and score updates overwrite rather than increment scores; revisit leaderboard semantics.

This repository illustrates a full-stack learning exercise, not a fully tested deployment.
