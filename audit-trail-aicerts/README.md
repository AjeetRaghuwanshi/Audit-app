Mini Audit Trail Generator

A micro full-stack web application that tracks text changes and automatically generates version history with added/removed words, timestamps, and metadata.

🚀 Features

📝 Content Editor with real-time text input

💾 Save Version button to store the current snapshot

📜 Version History Panel showing all text changes

🔍 Word-level diff detection (added & removed words)

🕒 Timestamp + UUID for each version

🌐 Full-stack flow (React frontend + Node.js/Express backend or Next.js API routes)

📂 Simple data storage (JSON / SQLite / In-memory)

🧠 How It Works

Whenever a user types text and clicks Save Version, the backend:

Compares the new text with the previous version

Extracts:

Added words

Removed words

Calculates:

Old length

New length

Generates a structured entry:

{
  "id": "uuid",
  "timestamp": "2025-11-26 13:40",
  "addedWords": ["example", "dashboard"],
  "removedWords": ["pilot"],
  "oldLength": 43,
  "newLength": 51
}


Stores the version and returns the full history.

🏛️ Tech Stack
Frontend

React / Next.js

Axios or Fetch API

Tailwind (optional)

Backend

Node.js + Express
OR

Next.js API Routes

Storage

JSON file
or

In-memory array (for demo)

📁 Folder Structure
/client
   /src
      App.jsx
      VersionHistory.jsx
      Editor.jsx

/server
   index.js
   versions.json
   diffHelper.js

🔗 API Endpoints
POST /save-version

Stores a new version and returns updated history.

GET /versions

Returns all saved versions.

⚙️ Running the Project
Backend
cd server
npm install
node index.js

Frontend
cd client
npm install
npm run dev

🧩 Diff Logic (Word-Level)

The backend splits text into individual words, compares old vs new arrays, and computes:

const added = newWords.filter(w => !oldWords.includes(w));
const removed = oldWords.filter(w => !newWords.includes(w));

📦 Deployment

You can deploy using:

Vercel (for React/Next.js)

Render / Railway (for Node backend)

🎯 Purpose of the Assignment

This project demonstrates:

Full-stack development capability

Ability to design small systems

Implementing custom logic instead of copying templates

Clean coding + clear architecture

Understanding of APIs, timestamps, UUID, data structures
