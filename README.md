# 📋 SOPilot — AI-Powered SOP Generator

> Describe any business process in plain English. Get a professional, structured Standard Operating Procedure document in seconds.

![Python](https://img.shields.io/badge/Python-3.11-blue?style=flat-square)
![Streamlit](https://img.shields.io/badge/Streamlit-UI-red?style=flat-square)
![Gemini](https://img.shields.io/badge/Google-Gemini%20AI-orange?style=flat-square)
![Status](https://img.shields.io/badge/Status-POC%20Complete-brightgreen?style=flat-square)

---

## 🧠 What Is This?

SOPilot is a rapid POC prototype that demonstrates how AI can eliminate one of the most tedious tasks in any business — writing Standard Operating Procedures manually.

A user describes a process in plain English. SOPilot uses a large language model to instantly generate a fully structured, professional SOP document — complete with Purpose, Scope, Roles, Steps, Edge Cases, and Success Metrics.

The output can be downloaded as a **PDF** or **TXT** file, and refined further using a natural language refinement loop.

---

## 🎯 Why I Built This

This project was built to demonstrate the **AI-assisted rapid prototyping workflow** — the same workflow used in enterprise GenAI tools:

```
Vision Document  →  AI-Generated Requirements  →  Code  →  Working Prototype
```

The full workflow is documented in this repo:
- `VISION.md` — the plain-English product vision (input to the AI tool)
- `BRD.md` — the AI-generated Business Requirements Document
- `app.py` — the working prototype built from those requirements

This mirrors exactly how tools like KIM work in enterprise settings — feed a vision, get structured output, iterate, deliver.

---

## ✨ Features

- **Plain English Input** — no forms, no dropdowns to fill, just describe the process
- **Department Context** — HR, Finance, Operations, IT, Sales, Other
- **Complexity Control** — Simple (1-page) or Detailed (multi-section)
- **8-Section Structured Output** — Title, Purpose, Scope, Roles, Pre-requisites, Steps, Edge Cases, Success Metrics
- **Refinement Loop** — type any instruction to refine and regenerate
- **PDF Export** — formatted, professional, ready to share
- **TXT Export** — plain text for further editing

---

## 🏗️ Architecture

```
User Input (Streamlit UI)
        ↓
Context + Complexity Selection
        ↓
Prompt Builder — constructs structured prompt
        ↓
Google Gemini API Call
        ↓
SOP Response Parser
        ↓
Streamlit Display + PDF Generator (ReportLab)
        ↓
Download Button / Refinement Loop
```

---

## 🛠️ Tech Stack

| Layer | Choice | Reason |
|---|---|---|
| Language | Python 3.11 | Fast to build and iterate |
| UI Framework | Streamlit | Professional UI with zero frontend code |
| AI Model | Google Gemini 2.0 Flash | Free tier, fast, high quality output |
| PDF Export | ReportLab | Pure Python PDF generation |
| Config | python-dotenv | Secure API key management |

---

## 🚀 Setup & Run Locally

**1. Clone the repo**
```bash
git clone https://github.com/YOUR_USERNAME/sopilot.git
cd sopilot
```

**2. Create a virtual environment**
```bash
python -m venv venv
source venv/bin/activate        # Mac/Linux
venv\Scripts\activate           # Windows
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Add your Gemini API key**

Create a `.env` file in the root folder:
```
GEMINI_API_KEY=your_gemini_api_key_here
```
Get a free key at: https://aistudio.google.com

**5. Run the app**
```bash
streamlit run app.py
```

App opens at `http://localhost:8501`

---

## 💡 Example Usage

Try this input to see it in action:

> *"Monthly expense report submission — employees submit receipts, manager approves, finance team processes reimbursement and updates accounts"*

- Department: **Finance**
- Complexity: **Detailed**
- Hit **Generate SOP**

Then try refining it with:
> *"Add an approval escalation process for expenses above ₹50,000"*

---

## 📁 Repo Structure

```
sopilot/
├── app.py              ← Main Streamlit application
├── requirements.txt    ← Python dependencies
├── VISION.md           ← Product vision document (AI input artifact)
├── BRD.md              ← AI-generated Business Requirements Document
├── .env                ← API key (not committed)
├── .gitignore          ← Ignores .env and cache files
└── README.md           ← This file
```

---

## 🔄 The Refinement Loop

One of the key features of SOPilot is the **refinement loop** — after generating an SOP, the user can type any natural language instruction to improve it:

- *"Make the steps more detailed"*
- *"Add a compliance and audit section"*
- *"Include escalation paths for exceptions"*
- *"Simplify the language for non-technical staff"*

This mirrors the human-in-the-loop review cycle used in enterprise AI prototyping workflows.

---

## 🔮 Future Improvements

- [ ] Save and manage multiple SOPs in a session
- [ ] Template library for common business processes
- [ ] Export to Word (.docx) format
- [ ] Role-based access and team collaboration
- [ ] Cloud deployment (Streamlit Cloud / Docker)

---

## 👤 Author

Built as a rapid POC prototype to demonstrate AI-assisted business workflow automation.

---

*SOPilot — Built with Google Gemini AI + Streamlit*
