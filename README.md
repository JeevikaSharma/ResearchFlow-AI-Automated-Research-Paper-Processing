# Automated Multilingual Research Submission Processor — Agentic AI System

An **Agentic AI-powered research submission processing platform** that automates the complete lifecycle of a research paper — from document ingestion and preprocessing to multilingual translation, metadata extraction, validation, plagiarism detection, RAG-based question answering, summarization, and Human-in-the-Loop review.

The system combines **ASP.NET Core Web API, Angular, Azure OpenAI, Azure AI Services, OCR, embeddings, Retrieval-Augmented Generation (RAG), and multi-agent architecture** to automate research-paper processing.

---

## 🚀 Overview

Research-paper submission involves several repetitive and time-consuming activities such as document validation, text extraction, translation, metadata extraction, plagiarism checking, summarization, and review.

This project automates these activities using an **Agentic AI pipeline**, where multiple specialized agents work together to process a research paper.

The system accepts a research paper as input and passes it through a sequence of AI-powered processing stages. Each agent is responsible for a specific task and produces structured output that is consumed by the next stage.

### Main Processing Flow

```text
Research Paper
      │
      ▼
Ingestion Agent
      │
      ▼
Pre-processing Agent
      │
      ▼
Translation Agent
      │
      ▼
Extraction Agent
      │
      ▼
Validation Agent
      │
      ├──────────────► Content Safety Agent
      │
      └──────────────► Plagiarism Detection Agent
      │
      ▼
RAG Agent
      │
      ▼
Summary Agent
      │
      ▼
Q&A Agent
      │
      ▼
Human Feedback Agent
      │
      ▼
Admin Review
```



---

## 🤖 Agent Architecture

The system consists of multiple specialized agents. Each agent performs a specific responsibility within the research-paper processing pipeline.

| #  | Agent                          | Responsibility                                                         |
| -- | ------------------------------ | ---------------------------------------------------------------------- |
| 1  | **Ingestion Agent**            | Receives and registers research-paper submissions                      |
| 2  | **Pre-process Agent**          | Performs file validation, text extraction, OCR, and language detection |
| 3  | **Translation Agent**          | Translates non-English content into English                            |
| 4  | **Extraction Agent**           | Extracts structured metadata from the research paper                   |
| 5  | **Validation Agent**           | Validates document structure and submission requirements               |
| 6  | **Content Safety Agent**       | Detects potentially unsafe or inappropriate content                    |
| 7  | **Plagiarism Detection Agent** | Performs similarity and plagiarism analysis                            |
| 8  | **RAG Agent**                  | Performs chunking, embedding generation, indexing, and retrieval       |
| 9  | **Summary Agent**              | Generates an AI-powered research-paper summary                         |
| 10 | **Q&A Agent**                  | Answers questions using retrieved document context                     |
| 11 | **Human Feedback Agent**       | Supports manual review and corrections                                 |

The agents are implemented as modular components with clearly defined responsibilities, making the system easier to maintain, test, and extend.

---

## 🏗️ Technology Stack

### Backend

* **C#**
* **.NET 8**
* **ASP.NET Core Web API**
* **Microsoft Semantic Kernel**
* **Azure OpenAI**
* **Azure AI Services**
* **Tesseract OCR**
* **PdfPig**
* **NPOI**
* **Open XML**
* **Swagger / OpenAPI**
* **REST APIs**

### Frontend

* **Angular 15**
* **TypeScript**
* **HTML5**
* **CSS3**
* **Angular Router**
* **Angular Forms**

### AI & Generative AI

* **Generative AI**
* **Agentic AI**
* **Large Language Models (LLMs)**
* **Prompt Engineering**
* **Retrieval-Augmented Generation (RAG)**
* **Embeddings**
* **Vector Search**
* **Multilingual AI**
* **Human-in-the-Loop (HITL)**
* **AI-powered Document Processing**

---

## 📂 Project Structure

```text
Automated-Multilingual-Research-Submission-Processor-Agentic-AI-System/
│
├── BackEnd/
│   │
│   ├── Agents/
│   │   ├── ContentSafetyAgent.cs
│   │   ├── ExtractionAgent.cs
│   │   ├── HumanFeedbackAgent.cs
│   │   ├── IngestionAgent.cs
│   │   ├── PlagiarismDetectionAgent.cs
│   │   ├── PreProcessAgent.cs
│   │   ├── QnAAgent.cs
│   │   ├── RagAgent.cs
│   │   ├── SummaryAgent.cs
│   │   ├── TranslationAgent.cs
│   │   ├── ValidationAgent.cs
│   │   └── Interfaces/
│   │
│   ├── Controllers/
│   │
│   ├── Endpoints/
│   │   └── DocumentEndpoints.cs
│   │
│   ├── Models/
│   │
│   ├── Pipeline/
│   │   └── DocumentPipelineOrchestrator.cs
│   │
│   ├── Plugins/
│   │
│   ├── Storage/
│   │
│   ├── Program.cs
│   ├── BackEnd.csproj
│   └── appsettings.json
│
├── FrontEnd/
│   │
│   ├── src/
│   │   └── app/
│   │       ├── components/
│   │       │   ├── admin/
│   │       │   ├── landing/
│   │       │   ├── login/
│   │       │   ├── user/
│   │       │   └── health-status/
│   │       │
│   │       ├── services/
│   │       ├── app-routing.module.ts
│   │       └── app.module.ts
│   │
│   ├── angular.json
│   └── package.json
│
└── README.md
```

---

## 🔐 Human-in-the-Loop Workflow

The system combines automated AI processing with human oversight to ensure that important decisions can be reviewed by an administrator.

```text
                    Document Processing
                            │
                            ▼
                    Automated AI Checks
                            │
                 ┌──────────┴──────────┐
                 │                     │
                 ▼                     ▼
             No Issues             Issues Found
                 │                     │
                 ▼                     ▼
          Continue Pipeline       Human Review
                                       │
                              ┌────────┴────────┐
                              ▼                 ▼
                           Approve            Reject
                              │                 │
                              └────────┬────────┘
                                       ▼
                                 Final Decision
```

### HITL Responsibilities

The Human-in-the-Loop layer allows administrators to:

* Review processing results.
* Inspect validation failures.
* Review content-safety findings.
* Review plagiarism or similarity results.
* Correct or verify extracted metadata.
* Approve valid submissions.
* Reject submissions that do not satisfy requirements.
* Provide feedback for further processing.

---

## 🔗 Overall System Architecture

```text
                         ┌─────────────────────┐
                         │     Angular UI      │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │  ASP.NET Core API   │
                         └──────────┬──────────┘
                                    │
                                    ▼
                    ┌──────────────────────────────┐
                    │ Document Pipeline            │
                    │ Orchestrator                 │
                    └──────────────┬───────────────┘
                                   │
       ┌───────────────────────────┼───────────────────────────┐
       │                           │                           │
       ▼                           ▼                           ▼
 Ingestion Agent           Pre-process Agent          Translation Agent
       │                           │                           │
       └───────────────────────────┼───────────────────────────┘
                                   │
                                   ▼
                           Extraction Agent
                                   │
                                   ▼
                           Validation Agent
                                   │
                     ┌─────────────┴─────────────┐
                     │                           │
                     ▼                           ▼
             Content Safety Agent       Plagiarism Agent
                     │                           │
                     └─────────────┬─────────────┘
                                   │
                                   ▼
                               RAG Agent
                                   │
                         ┌─────────┴─────────┐
                         │                   │
                         ▼                   ▼
                   Summary Agent        Q&A Agent
                         │                   │
                         └─────────┬─────────┘
                                   │
                                   ▼
                         Human Feedback Agent
                                   │
                                   ▼
                              Admin Review
```





---

## ✨ Key Features

* 📄 Automated research-paper document ingestion
* 📚 Support for PDF, DOCX, and DOC documents
* 🔍 Document preprocessing and text extraction
* 🖼️ OCR support for scanned documents
* 🌍 Automatic language detection
* 🔄 Multilingual document translation
* 🧠 AI-powered metadata extraction
* ✅ Research-paper structure and requirement validation
* 🛡️ Content safety analysis
* 🔎 Plagiarism and similarity detection
* 📚 Retrieval-Augmented Generation (RAG)
* 🧩 Intelligent text chunking
* 🔢 Embedding generation
* 🗃️ Vector similarity search
* ✨ AI-generated research-paper summaries
* 💬 Context-aware document Q&A
* 👤 Human-in-the-Loop (HITL) review
* ✔️ Admin approval and rejection workflow
* 📝 Audit and processing logs
* ❤️ Backend health monitoring
* 📖 Swagger / OpenAPI support


---


## 👩‍💻 Author

**Jeevika Sharma**

Agentic AI / Generative AI project focused on automated multilingual research-submission processing using **Azure OpenAI, LLMs, RAG, embeddings, and multi-agent architecture**.
