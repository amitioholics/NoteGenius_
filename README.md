# NoteGenius — AI-Powered Study Assistant

NoteGenius is a modern, AI-first note-taking app that turns raw notes into learning superpowers. It generates smart summaries, extracts key concepts, and creates MCQ quizzes — all in a polished, responsive UI.

Made by: **Amit Singh Rajput**  
Contact: **amitsinghrajput263@gmail.com**

---

## ✨ Features

- Smart Summaries  
  Create comprehensive and structured summaries from your study notes.

- Keyword Extraction  
  Identify and visualize key concepts with a clean, copy-to-clipboard grid.

- MCQ Quiz Generator  
  Turn notes into multiple-choice questions with scoring and explanations.

- Math Practice Lab  
  Upload math problems (PDF/Images) or type them out to automatically extract questions and generate high-quality practice variations with step-by-step AI solutions.

- Document Extraction  
  Seamlessly upload and extract text from PDF, DOCX, and PPTX files to instantly create study notes.

- Offline Resilience  
  Graceful local fallbacks when AI API is unavailable or rate-limited.

- Smooth, Modern UI  
  Gradient theming, glass-morphism, micro-interactions, and responsive design.

---

## 🧠 Tech Stack

- Framework: Next.js 15 (App Router), React, JavaScript  
- Styling: Tailwind CSS, shadcn/ui  
- AI: Vercel AI SDK with OpenAI models (with local fallbacks)  
- Data: Lightweight JSON (demo) via Next.js Route Handlers  
- Tooling: Vercel (deploy), ESLint

---

## 🚀 Getting Started

### 1) Clone and install

```bash
git clone <your-repo-url>
cd notegenius
pnpm install
# or: npm install / yarn
```

### 2) Environment variables

Create the following environment variables in your environment (or in Vercel Project Settings → Environment Variables):

- `OPENAI_API_KEY` — required for AI features (the app still works without it using local fallbacks)
- `BLOB_READ_WRITE_TOKEN` — only if you add Vercel Blob features later

### 3) Run the dev server

```bash
pnpm dev
# or: npm run dev / yarn dev
```

Visit http://localhost:3000

---

## 🧪 How to Use

1) Create a new note using “New Note”  
2) Add your content in the Editor tab  
3) Use the tabs:
   - Summary: Generate a detailed summary  
   - Keywords: Extract and copy key concepts  
   - Quiz: Generate MCQs, select answers, and view score  
   - Math Lab: Upload math problems or type them to generate AI variations and practice.
4) Use "Upload Document" to extract text directly from PDF, DOCX, or PPTX files.
5) Add tags for better organization

Notes are stored in a local JSON file (demo) and managed via API endpoints.

---

## 📦 Project Structure (key files)

- `app/page.jsx` — main UI, tabs, and interactions  
- `lib/ai-helpers.js` — AI integration + local fallback algorithms  
- `app/api/notes/route.js` — JSON-based CRUD for demo storage  
- `components/*` — Note editor, list, dialogs, keyword cards, math lab, etc.  
- `app/globals.css` — theme tokens, animations, micro-interactions

---

## 🔌 API (Demo)

Base path: `/api/notes`

- GET `/api/notes` — fetch all notes  
- POST `/api/notes` — create a note  
  - body: `{ title: string, content: string, tags?: string[] }`
- PUT `/api/notes` — update a note  
  - body: `{ id: string, title: string, content: string, tags: string[] }`
- DELETE `/api/notes?id=<noteId>` — delete a note

Data is saved at `/data/notes.json` (auto-created).

---

## 🤖 AI Details

- Default: OpenAI model via the Vercel AI SDK  
- Fallbacks: If `OPENAI_API_KEY` is missing or API errors occur, local algorithms provide:
  - Summary generation (sentence scoring + keyword weighting)
  - Keyword extraction (frequency-based, common-word filtering)
  - MCQ generation (contextual distractors + definitions)

This ensures the app remains usable even without external AI during demos.

---

## 🌐 Deployment (Vercel)

1) Push to GitHub  
2) Import repo in Vercel → “Deploy”  
3) Add env vars (`OPENAI_API_KEY`) in Vercel Project Settings  
4) Redeploy if env vars were added after the first build

Optional  
- Try to claim a neat domain like `notegenius.vercel.app` or add a custom domain

---

## 🖼️ Screenshots

Add your screenshots in `/public/screenshots` and link them here:

- Home / New Note  
- Editor  
- Summary Tab  
- Keywords Grid  
- MCQ Quiz + Score

```md
![Home](public/screenshots/home.png)
![Editor](public/screenshots/editor.png)
![Summary](public/screenshots/summary.png)
![Keywords](public/screenshots/keywords.png)
![Quiz](public/screenshots/quiz.png)
```

---

## 🗺️ Roadmap

- Rich text editor (headings, lists, code blocks)  
- Cloud auth + DB (e.g., Supabase / MongoDB)  
- Export notes (PDF/Markdown)  
- Spaced repetition and flashcards  
- Multi-language support

---

## 👤 Author

**Amit Singh Rajput**  
Email: `amitsinghrajput263@gmail.com`  
LinkedIn: <add-your-linkedin-urlhttps://www.linkedin.com/in/amit-kumar-0a6617258>  
GitHub: <add-your-github-urlhttps://github.com/amitioholics/NoteGenius>

---

## 📝 License

MIT License — © Amit Singh Rajput

You are free to use, modify, and distribute this software with attribution.

---
