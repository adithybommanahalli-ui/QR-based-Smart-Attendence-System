# QR-Based Smart Attendance System

This repository contains a FastAPI backend and a React + Vite frontend for a QR-based smart attendance system.

## Setup Guide

Follow these steps one by one to get both servers running.

### 1. Clone the repository

```bash
git clone https://github.com/VinayakaK2/QR-based-Smart-Attendence-System.git
cd QR-based-Smart-Attendence-System
```

### 2. Backend setup

1. Open a terminal in the `backend` folder:

```bash
cd backend
```

2. Install backend Python dependencies:

```bash
pip install -r requirements.txt
```

3. Install required system libraries for OpenCV and DeepFace support (Linux):

```bash
sudo apt update
sudo apt install -y libglib2.0-0 libsm6 libxext6 libxrender-dev libgomp1 mesa-common-dev libgl1-mesa-dev
```

> If you are using a remote environment or Codespaces, make sure the container can install these packages.

4. Start the backend server:

```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

5. Verify the backend is running by opening:

```text
http://127.0.0.1:8000/
```

### 3. Frontend setup

1. Open a new terminal in the `frontend` folder:

```bash
cd frontend
```

2. Install frontend dependencies:

```bash
npm install
```

3. Start the frontend development server:

```bash
npm run dev
```

4. Open the frontend in a browser at:

```text
http://localhost:5173/
```

### 4. Common issues

- `ERR_CONNECTION_REFUSED` to `localhost:8000`:
  - Make sure the backend server is running on port `8000`
  - If you are in a container or remote environment, ensure port `8000` is forwarded to the host

- CORS / network errors from the frontend:
  - The frontend is configured to proxy `/api` requests to the backend in development
  - Confirm `frontend/vite.config.js` contains the `/api` proxy to `http://127.0.0.1:8000`

### 5. Notes for team members

- Start the backend first, then start the frontend.
- Use separate terminals for each server.
- If you make changes in the backend or frontend code, the development servers automatically reload.

### 6. Repository structure

- `backend/` - FastAPI backend application
- `frontend/` - React + Vite frontend application

---

If you need help with environment-specific setup (Codespaces, Docker, or Windows), ask for additional instructions.
