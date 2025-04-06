# AIClassroomAid
## Enhancing Textbooks with AI

A hackathon project designed to assist teachers in classroom learning by intelligently augmenting standard textbooks (starting with Class 9 NCERT Physics) with contextual, interactive, and real-world content. Our goal is to bridge learning gaps without disrupting the existing curriculum structure.

---

## 🚀 Demo Scope
For the hackathon, we’re showcasing:
- Class 9 NCERT Physics
- Focus on "Newton's Laws of Motion"
- Real-time PDF augmentation
- Teacher-facing UI with enhanced explanations, analogies, and Q&A

---

## ✨ Key Features

- 📄 **PDF Viewer**: Open textbook directly within the platform  
- 🔍 **Auto-highlight**: Detects key headings like "First Law of Motion"  
- 🧠 **Augmented Panel**: Displays:
  - Clarification of common misconceptions
  - Real-world examples & analogies
  - Discussion prompts
  - Conceptual biases (if any)
- 💬 **Ask a Question**: Custom input field powered by AI-based Q&A  
- 🌐 **Curriculum-Aligned**: Built to support NCERT, with a scalable path for global curriculum

---

## 🧠 Tech Stack

### Frontend
- `React.js` + `Tailwind CSS` ⚛️🎨  
- Split layout for textbook + augmented content

### Backend
- `FastAPI` ⚡ – API layer
- `Docker` 🐳 – Containerized app

### AI/NLP
- `spaCy` 🧬 – Topic recognition
- `Hugging Face Transformers` 🤗 – Summarization & Q&A
- `Haystack` 📚 – Context-aware retrieval & questioning
- `PyMuPDF`, `pdfplumber` 📄 – PDF parsing
- `Tesseract OCR` 🔍 – Scanned PDF support

---

## 🏗️ Architecture

```mermaid
flowchart TB

    subgraph Frontend
        A1[Teacher opens NCERT PDF]
        A2[Highlighted PDF Viewer]
        A3[Augmented Content Panel]
        A4[Ask Custom Question]
    end

    subgraph Backend
        B1[FastAPI: Request Handler]
        B2[PDF Parser / OCR / Routing]
    end

    subgraph AI Engine
        C1[PyMuPDF / pdfplumber]
        C2[Tesseract OCR]
        C3[spaCy Topic ID]
        C4[HuggingFace Transformers]
        C5[Haystack QA Engine]
        C6[Augmentation Generator]
    end

    subgraph Data
        D1[NCERT PDFs]
        D2[Teacher Queries]
        D3[Future: Knowledge Base]
    end

    A1 --> B1 --> B2
    A4 --> B1
    B2 --> C1 & C2 --> C3 --> C6 --> A3
    A2 <-- B2
    B1 --> C4
    A4 --> C5 --> A3

    D1 --> B2
    D2 --> C5
