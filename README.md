# StoryStudio

StoryStudio is an AI-powered web application that turns story ideas into visual narratives. It uses a Flask backend (Python) and a Next.js frontend (React).

## 🚀 Features
- **AI Story Generation**: Powered by Cohere.
- **Visual Scene Generation**: Powered by Stability AI.
- **Narrative Conversion**: Converts text stories into structured scenes with images.

## 🛠 Tech Stack
- **Frontend**: Next.js, TailwindCSS, React
- **Backend**: Flask, Gunicorn
- **AI Services**: Cohere API, Stability AI (DreamStudio)

---

## 💻 Local Setup

### Prerequisites
- Node.js & npm
- Python 3.9+

### 1. Backend Setup
Navigate to the backend directory and set up the Python environment:

```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Create a `.env` file in the `backend/` directory:
```
COHERE_API_KEY=your_cohere_key_here
STABILITY_API_KEY=your_stability_key_here
```

Run the backend server:
```bash
python app.py
# Server runs on http://127.0.0.1:5001
```

### 2. Frontend Setup
Navigate to the frontend directory:

```bash
cd frontend
npm install
```

Create a `.env.local` file in the `frontend/` directory if needed (usually for backend URL):
```
NEXT_PUBLIC_API_URL=http://127.0.0.1:5001
```

Run the frontend:
```bash
npm run dev
# App runs on http://localhost:3000
```

---

## 🌍 Deployment

### Deploy Backend (Render / Heroku)
The backend includes a `Procfile` for easy deployment.
1. Push this repository to GitHub.
2. Connect the repo to **Render** or **Heroku**.
3. Set the **Root Directory** to `backend`.
4. Set the **Build Command** to `pip install -r requirements.txt`.
5. Set the **Start Command** to `gunicorn app:app`.
6. Add your Environment Variables (`COHERE_API_KEY`, `STABILITY_API_KEY`) in the dashboard.

### Deploy Frontend (Vercel)
1. Push this repository to GitHub.
2. Go to **Vercel** and import the project.
3. Set the **Root Directory** to `frontend`.
4. Vercel automatically detects Next.js.
5. Add `NEXT_PUBLIC_API_URL` environment variable pointing to your **deployed backend URL** (e.g., `https://storystudio-backend.onrender.com`).
6. Deploy!

## ⚠️ Troubleshooting
- **CORS Errors**: Ensure your backend `app.py` has CORS enabled for your frontend domain.
- **API Keys**: If generation fails, check your API keys in the `.env` files.





RUN FRONTEND - npm run dev
RUN BACKEND  - source venv/bin/activate
               python app.py

