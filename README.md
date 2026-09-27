# 🎬 AI Video & Meeting Intelligence Assistant

An AI-powered meeting and video intelligence application that converts YouTube videos or local media into structured, searchable knowledge.

The system can transcribe audio, generate meeting summaries, extract action items and key decisions, identify unresolved questions, and allow users to ask questions about the transcript using Retrieval-Augmented Generation (RAG).

---

## 🚀 Features

- 🎥 Process YouTube videos and local audio/video files
- 🎙️ English transcription using OpenAI Whisper
- 🌐 Hinglish transcription/translation using Sarvam AI
- 📝 Generate professional meeting summaries
- ✅ Extract action items with owners and deadlines
- 🎯 Identify key decisions
- ❓ Detect unresolved questions and follow-up topics
- 🔎 Semantic transcript search using embeddings
- 🧠 RAG-based question answering
- 💾 Persistent local vector database using ChromaDB
- 💬 Interactive Streamlit interface

---

# 🧠 How It Works

The application follows this pipeline:

```text
YouTube URL / Local Media
          │
          ▼
   Audio Processing
   yt-dlp + FFmpeg
          │
          ▼
      WAV Audio
          │
          ▼
    Audio Chunking
          │
          ▼
 ┌───────────────────┐
 │   Transcription   │
 │                   │
 │ English → Whisper │
 │ Hinglish → Sarvam │
 └───────────────────┘
          │
          ▼
      Transcript
          │
          ├────────────► Meeting Title
          │
          ├────────────► Summary
          │
          ├────────────► Action Items
          │
          ├────────────► Key Decisions
          │
          └────────────► Open Questions
          │
          ▼
     Text Chunking
          │
          ▼
 HuggingFace Embeddings
   all-MiniLM-L6-v2
          │
          ▼
       ChromaDB
          │
          ▼
       Retriever
          │
          ▼
 Relevant Transcript Chunks
          │
          ▼
      Mistral LLM
          │
          ▼
   Grounded RAG Answer
