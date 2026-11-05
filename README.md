# StudyMate AI — Team Tricksters

StudyMate AI is a Next.js 15 + TypeScript study platform using Google Gemini and optional Supabase storage.

## Local setup (VS Code)

1. Install **Node.js 20 LTS**.
2. Open this folder in VS Code and run `npm install` in the terminal.
3. Copy `.env.example` to `.env.local`.
4. Fill in your own valid credentials. Never share or commit `.env.local`.
5. Run `npm run dev` and open `http://localhost:3000/auth`.

### Required environment variables

- `GEMINI_API_KEY`: a Google Gemini API key compatible with the selected API mode.
- `GEMINI_MODEL`: use a supported model ID such as `gemini-2.5-flash` (do not add a `gemini/` provider prefix).
- `SESSION_SECRET`: a random secret of at least 32 characters.
- `ADMIN_ID` and `ADMIN_PIN`: private admin credentials.

Supabase variables are optional for local-persistent mode, but are required if you want Supabase database/storage. Configure them in `.env.local` and in Netlify's environment variables for the deployed site.

## Deploying on Netlify

Set the same required environment variables in **Netlify → Site configuration → Environment variables**, then trigger a fresh deploy. Do not put API keys or PINs in `netlify.toml`, frontend code, screenshots, or chat messages.

## Security note

This source archive previously contained a local `.env.local` file. It has been removed from this cleaned archive. Rotate any Gemini, Supabase service-role, or other credentials that were present in the original archive before using this project in production.

---

## Core Modules & Features

1. **Google Account & Student ID Authentication** (with 1-year persistent session & auto-login)
2. **Student Dashboard**
3. **Study Materials & Multi-Format Extraction Pipeline** (PDF, DOCX, PPTX, XLSX, CSV, TXT, MD, Images, Audio, Video)
4. **Independent AI Services** (strictly isolated schemas & storage):
   - **AI Detailed Notes** (`/dashboard/ai-notes`)
   - **Rapid Short Notes** (`/dashboard/short-notes`)
   - **Source-Grounded AI Chatbot** (`/dashboard/chat`)
   - **Interactive Flip Flashcards** (`/dashboard/flashcards`)
   - **Practice Questions & Answer Keys** (`/dashboard/questions`)
5. **Three Extra Deterministic Features**:
   - **AI Study Planner** (`/dashboard/planner`)
   - **Focus Mode + Pomodoro Timer** (`/dashboard/focus`)
   - **Smart SM-2 Spaced Repetition Revision System** (`/dashboard/revision`)
6. **Admin Dashboard (`/admin/dashboard`) & Supreme SuperAdmin Command Center (`/superadmin/dashboard`)**
