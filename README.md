# NVIDIA Certification Study Tools

Interactive, browser-based study tools for NVIDIA AI certification exams. No install required — just open in your browser.

## Live Site

**[Open Study Tools](https://laraarias.github.io/NVIDIA-certificator/)**

## Certifications Covered

| Cert | Full Name | Status |
|------|-----------|--------|
| **NCA-AIIO** | AI Infrastructure and Operations (Associate) | Study suite + practice exam |
| **NCA-GENL** | Generative AI LLM (Associate) | Glossary terms + study guide |
| **NCP-GENL** | Generative AI LLM (Professional) | Glossary terms + study guide |

## What's Included

### NCA-AIIO Study Suite
- **Study Mode** — Flashcard-style review with filtering by domain, mastery level, and flags
- **Test Mode** — Timed practice exams simulating real exam conditions (50 questions, 60 min)
- **Glossary** — 117 terms across all 3 certs, filterable by certification, lifecycle stage, and category
- **Progress Tracking** — Accuracy stats, mastery levels, and test history saved in localStorage

### Practice Exam
- Standalone exam format with immediate scoring and explanations

### Glossary Categories
- Hardware & GPUs, Networking, Software & Frameworks, Infrastructure & Operations
- LLM Architecture, Prompt Engineering, Data & Preprocessing, Training & Fine-Tuning
- Optimization, Evaluation & Metrics, Deployment & Monitoring, AI Ethics & Safety, Core ML Concepts

## Usage

**Option 1 — GitHub Pages (recommended):**
Visit [laraarias.github.io/NVIDIA-certificator](https://laraarias.github.io/NVIDIA-certificator/)

**Option 2 — Local:**
Clone and open any `.html` file directly in your browser. No server needed.

```bash
git clone https://github.com/LaraArias/NVIDIA-certificator.git
open NVIDIA-certificator/index.html
```

## Tech

- Single-file HTML apps (React 18 via CDN + Babel)
- Zero dependencies, zero build step
- All progress saved to localStorage
- Works offline after first load
