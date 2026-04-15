#  AI Resume Screening System with LangChain & LangSmith

##  Overview
This project implements an **AI-powered Resume Screening System** that evaluates candidates against a given job description.

It leverages:
- **LangChain** for building modular LLM pipelines
- **LangSmith** for tracing, debugging, and monitoring
- **OpenAI / HuggingFace APIs** for language model capabilities

The system processes resumes and outputs:
-  Fit Score (0–100)
-  Detailed Explanation (Why the score was assigned)

---

##  Objective
Build a production-style GenAI system that:
- Extracts relevant information from resumes
- Matches it with job requirements
- Scores candidates objectively
- Provides explainable outputs
- Enables full pipeline tracing

---

##  System Architecture

```
Resume + Job Description
        ↓
Skill Extraction
        ↓
Matching Logic
        ↓
Scoring Engine
        ↓
Explanation Generator
        ↓
Final Output + LangSmith Tracing
```

---

##  Project Structure

```
resume-screening-system/
│
├── prompts/
│   ├── extraction_prompt.py
│   ├── matching_prompt.py
│   ├── scoring_prompt.py
│   └── explanation_prompt.py
│
├── chains/
│   ├── extraction_chain.py
│   ├── matching_chain.py
│   ├── scoring_chain.py
│   └── explanation_chain.py
│
├── data/
│   ├── strong_resume.txt
│   ├── average_resume.txt
│   ├── weak_resume.txt
│   └── job_description.txt
│
├── main.py
├── requirements.txt
└── README.md
```

---

##  Installation

```bash
git clone https://github.com/your-username/resume-screening-system.git
cd resume-screening-system
pip install -r requirements.txt
```

---

##  Environment Variables

```bash
export OPENAI_API_KEY="your_api_key"
export LANGCHAIN_TRACING_V2=true
export LANGCHAIN_API_KEY="your_langsmith_key"
```

---

##  Pipeline Implementation

### 1. Skill Extraction
Extracts:
- Skills
- Experience
- Tools

### 2. Matching Logic
- Compares extracted data with job description
- Identifies overlaps and gaps

### 3. Scoring
- Assigns score between **0–100**
- Based on:
  - Skill match
  - Experience relevance
  - Tool familiarity

### 4. Explanation
- Justifies the assigned score
- Highlights:
  - Strengths
  - Missing requirements

---

##  LangChain Usage

This project uses:
- `PromptTemplate`
- LCEL (LangChain Expression Language)
- `.invoke()` method for execution

Example:

```python
chain.invoke({"resume": resume, "job_description": jd})
```

---

##  LangSmith Tracing (Mandatory)

LangSmith is used to:
- Track each pipeline step
- Debug incorrect outputs
- Monitor LLM behavior

### Requirements:
- At least **3 runs**:
  - Strong candidate
  - Average candidate
  - Weak candidate

### Must Show:
- Full pipeline execution
- Intermediate outputs
- One debugging case (incorrect output + fix)

---

##  Prompt Engineering Strategy

- Clear and structured instructions
- Constrained outputs
- No hallucinations

### Rule Example:
> Do NOT assume skills not present in the resume

---

##  Sample Output

```json
{
  "score": 82,
  "explanation": "Candidate has strong Python and ML experience but lacks deployment experience..."
}
```

---

##  Bonus Features

- Few-shot prompting
- Structured JSON outputs
- LangSmith tagging

---

##  Requirements

```txt
langchain
openai
langsmith
python-dotenv
```

---

##  Submission Checklist

-  Complete code (GitHub)
-  LangSmith tracing screenshots
-  Report/documentation
-  LinkedIn post

---

##  Evaluation Criteria

| Criteria                     | Weight |
|----------------------------|--------|
| Pipeline Design             | 20%    |
| LangChain Implementation    | 20%    |
| Scoring & Logic             | 15%    |
| Explainability              | 15%    |
| LangSmith Tracing           | 15%    |
| Code Quality                | 10%    |
| Bonus                       | 5%     |

---

##  Important Rules

- ❌ No hardcoded outputs
- ❌ No hallucinated assumptions
- ❌ No incomplete pipeline
- ✅ Must include tracing
- ✅ Must include explanation logic

---

##  Final Insight

This project transitions you from:


