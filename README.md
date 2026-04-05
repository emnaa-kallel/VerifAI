📄 VerifAI — AI-Powered Misinformation Detector
🚀 Overview

VerifAI is a web application built during a hackathon to detect whether online content (image + text) is real, misleading, or uncertain.

It combines:

🖼️ Image analysis
📝 Text extraction
🌐 Reverse image search
🧠 AI reasoning

👉 To provide a clear verdict, a confidence score, and an explainable analysis.

🎯 Objective

In today’s digital world, content can easily be manipulated or taken out of context.

VerifAI helps bridge the gap between information and truth by verifying:

Image origin
Context consistency
Caption accuracy
🔁 Workflow
🟢 Input

The user can:

Paste a social media URL (Facebook, Twitter, etc.)
Upload an image
🔵 Processing Pipeline
1. Extraction
📷 Image retrieval
📝 Text extraction:
Scraping (URL)
OCR (image)
2. Reverse Image Search
Find:
Original source
Publication date
Context
3. AI Analysis (Core)
Compare:
Caption / claim
Real context of the image
🔴 Output
✅ Verdict
Real
Misleading
Uncertain
📊 Confidence Score
Example: 82%
💬 Explanation
Detected inconsistencies
Context mismatch
Clear reasoning
🧠 AI Logic

The AI detects:

⏳ Temporal inconsistencies
🌍 Geographical inconsistencies
🔄 Caption vs image mismatch
📌 Prompt Used:
You are an AI fact-checking assistant.

You are given:
1. A caption or claim
2. Context information from reverse image search

Your task:
- Determine if the content is consistent or misleading
- Identify if the image is reused from another context
- Compare time, location, and event

Return STRICTLY in this format:

Verdict: (Real / Misleading / Uncertain)
Confidence Score: (0-100)

Explanation:
- Point 1
- Point 2
- Point 3

Final Conclusion:
(1-2 sentences max, very clear)

🧰 Tech Stack
🎨 Frontend:
React
Tailwind CSS (optional)

🧠 Backend:
FastAPI (Python)

🤖 AI:
OpenAI API / Groq

🔍 OCR:
  pytesseract
  easyocr

🌐 Reverse Image Search:
  SerpAPI (Google Images)
  Bing Visual Search

⚙️ Architecture
Frontend (React)
      ↓
Backend (FastAPI)
      ↓
-------------------------
| OCR                  |
| Reverse Image Search |
| LLM (AI)             |
-------------------------
      ↓
   JSON Result
      ↓
Frontend Display

📁 Project Structure
verifai/
│
├── Backend/
│   ├── api/
│   │   └── routes.py
│   ├── app/services/
│   ├── core/
│   │   └── pipeline.py
│   ├── models/
│   │   └── schemas.py
│   ├── services/
│   │   ├── context_service.py
│   │   ├── image_service.py
│   │   ├── llm_service.py
│   │   ├── reasoning_ai.py
│   │   ├── reverse_image.py
│   │   ├── url_service.py
│   │   └── ocr.py
│   ├── uploads/
│   ├── main.py
│   └── test_unit_ocr.py
│
├── frontend/
│   ├── public/
│   └── src/
│       ├── App.js
│       └── index.js
│
├── requirements.txt
└── README.md

⚡ Installation
1. Clone the repo:
git clone https://github.com/your-username/verifai.git
cd verifai

3. Backend setup:
cd Backend
python -m venv venv
venv\Scripts\activate   # Windows

pip install -r requirements.txt

3. Run backend:
uvicorn main:app --reload

4. Frontend setup:
cd frontend
npm install
npm start

🔌 API Endpoints
POST /analyze:
Analyze content (URL or image)

POST /upload:
Upload an image for analysis

🧪 Demo Cases
✅ Case 1 (Misleading)
Old image + recent caption
👉 Result: Misleading
✅ Case 2 (Real)
Matching image + caption
👉 Result: Real
👥 Team Roles

👩‍💻 Frontend Dev:
  UI / UX
  Results display
👨‍💻 Backend Dev:
  FastAPI
  API routes
  LLM integration
🧠 AI / Data Dev:
  OCR
  Reverse image search
  Data structuring

⏱️ Hackathon Plan (20h):
  Time	    Task
  0–5h	    Setup + skeleton
  5–10h	    OCR + scraping
  10–15h	  Reverse image + pipeline
  15–20h	  UI + debug + demo
