<div align="center">

# 🤖 AI-901 Exam Simulator

[![Live exam](https://img.shields.io/badge/%E2%96%B6%20Take%20the%20exam-chrismunnps.github.io-7c3aed?style=for-the-badge)](https://chrismunnps.github.io/exam-sim/ai-901/)
[![Questions](https://img.shields.io/badge/questions-180-2563eb?style=for-the-badge)](#-question-bank)
[![Pass mark](https://img.shields.io/badge/pass%20mark-700%20%2F%201000-0d9488?style=for-the-badge)](#-scoring-and-review)
[![Exam time](https://img.shields.io/badge/exam%20time-60%20minutes-f59e0b?style=for-the-badge)](#-exam-at-a-glance)
[![Case studies](https://img.shields.io/badge/case%20studies-2-0891b2?style=for-the-badge)](#-case-studies)
[![Offline](https://img.shields.io/badge/offline-double--click-16a34a?style=for-the-badge)](#-run-it-locally)

### Microsoft Azure AI Fundamentals · 180 questions · 2 case studies · runs entirely in the browser

**▶ Live exam: https://chrismunnps.github.io/exam-sim/ai-901/**

</div>

---

## 🚀 Executive summary

A free, full-length practice exam for **Exam AI-901: Microsoft Azure AI Fundamentals**, built from the two Microsoft Learn AI-901 learning paths. It recreates the real sitting closely enough to be useful: a weighted 45-question draw, a 60-minute clock, scaled scoring against the 700 pass mark, two case studies, and eight concept diagrams.

Everything runs client-side. There is no account, no install, no server, no analytics, and no network call after the page loads — scores and review history stay in the visitor's own browser.

The simulator is seven runtime files, identical in the repository and on the live site:

> **🌐 Live site: https://chrismunnps.github.io/exam-sim/ai-901/**
> Served by GitHub Pages from the portfolio repo's `exam-sim/ai-901/` folder — the seven runtime files in this repository are exactly what is deployed.

It is an independent study tool. It is not affiliated with, endorsed by, or connected to Microsoft.

---

## ✨ Why this one is different

🧭 **It behaves like the real exam.** Forty-five questions drawn by domain weight, 80 seconds each, a running clock, flag-for-review, a question palette, and submit-on-timeout.

🧠 **Explanations teach, not just score.** Every item carries a rationale, a note on why each distractor is wrong, an exam tip, and the exam skill area it maps to.

🧩 **Two case studies.** Twelve questions hang off shared scenarios — Contoso's multilingual customer-service operation and Fabrikam's retail AI initiative — so you practise holding context across a case, the way the real exam does.

🖼️ **Eight AI-specific diagrams.** Inline SVG covers the ML lifecycle, classification vs regression, supervised vs unsupervised, the Azure AI service map, the NLP flow, detection vs classification, RAG architecture, and prompt structure. Every diagram question also explains the concept in words.

✅ **Multi-answer items are all-or-nothing.** Nine `Select two` questions are graded exactly as strictly as the exam grades them.

🔁 **A spaced-review queue.** Wrong answers come back on a schedule instead of disappearing, so weak domains get revisited without re-running whole exams.

🌓 **Light and dark themes.** A top-bar switch, remembered per browser, following the OS until you choose. Printing always forces black-on-white.

⌨️ **Keyboard-first.** `A`–`D` to answer, arrows to navigate, `F` to flag, plus a visible focus ring and a skip link.

📴 **Genuinely offline.** Double-click the page and it works with the network unplugged. No bundler, no local server, no runtime dependencies.

---

## 🎯 Exam at a glance

| | |
|---|---|
| **Certification** | Microsoft Certified: Azure AI Fundamentals |
| **Exam** | AI-901 — Microsoft Azure AI Fundamentals |
| **Questions in bank** | 180 (168 standalone + 12 case-study) |
| **Default attempt** | 45 questions: 8 fundamentals, 12 machine learning, 8 vision, 7 language, 10 generative AI |
| **Time limit** | 80 seconds per question — 60 minutes for the default draw |
| **Passing score** | 700 / 1,000 (scaled from percentage correct) |
| **Review** | Every question after submission, with explanations and sources |
| **Prerequisites** | A browser. That is the whole list. |

---

## 📚 Question bank

| Domain | Standalone | Case items | Weight | IDs |
|---|---:|---:|---|---|
| AI fundamentals | 28 | 2 | 15–20% | Q1–Q28 |
| Machine learning | 50 | 0 | 25–30% | Q29–Q78 |
| Computer vision | 28 | 2 | 15–20% | Q79–Q106 |
| Natural language | 26 | 4 | 15–20% | Q107–Q132 |
| Generative AI | 36 | 4 | 20–25% | Q133–Q168 |
| Case studies | — | 12 | — | Q169–Q180 |
| **Total** | **168** | **12** | | **180** |

The domain totals — **30 fundamentals, 50 machine learning, 30 vision, 30 language, 40 generative AI** — match the blueprint, including the case items that count towards each domain. A default draw uses the midpoints of the skills-measured ranges (17.5 / 27.5 / 17.5 / 17.5 / 22.5), which yields **8 / 12 / 8 / 7 / 10**.

**Question mix:** scenario-led choices, service recognition ("which service should you use"), comparison pairs, ten diagram-backed items, and nine `Select two` multiple-response questions. The bank deliberately stops short of coding, Python, model tuning, and ML mathematics — AI-901 tests recognition and matching, not implementation.

### 🗂️ Case studies

| Case | Questions | Scenarios |
|---|---|---|
| Contoso Customer Service | Q169–Q174 | Sentiment analysis, translation, summarisation, conversational AI, intent recognition, fairness |
| Fabrikam Retail AI | Q175–Q180 | Invoice extraction, shelf object detection, product-copy generation, Azure OpenAI, RAG, content filters |

The case questions carry their domain weight, so a full draw still reflects the AI-901 skills outline.

---

## 🧾 Cheat sheets

Five printable one-page refreshers, one per domain, plus a single self-contained print pack. They sit in this repository alongside the simulator; only the seven runtime files are needed to run the exam.

| File | Covers |
|---|---|
| `04-CHEAT-SHEET-FUNDAMENTALS.md` | AI vs ML vs deep learning vs generative AI, workloads, task types, vision scenarios, responsible AI, requirement matching |
| `05-CHEAT-SHEET-MACHINE-LEARNING.md` | Features and labels, data splits, supervised vs unsupervised, accuracy / precision / recall / F1 / RMSE / MAE, overfitting, Azure ML assets, endpoints, MLOps |
| `06-CHEAT-SHEET-VISION.md` | Azure AI Vision, classification vs detection, OCR vs Document Intelligence, prebuilt and custom models, Custom Vision, Face, service selection |
| `07-CHEAT-SHEET-NLP.md` | Azure AI Language, sentiment and opinion mining, entities vs key phrases, summarisation, question answering vs CLU, translation and speech |
| `08-CHEAT-SHEET-GENERATIVE-AI.md` | Tokens and context windows, prompt anatomy, generation settings, Azure OpenAI and Foundry, RAG, hallucination, fine-tuning vs RAG, safety, Copilot |
| `09-CHEAT-SHEETS.html` | All five sheets laid out as A4 pages — open and print |

Open `09-CHEAT-SHEETS.html` in a browser and choose **Print all five sheets**. Each domain fits one A4 page at two columns, type is set for paper rather than screen, and the toolbar and background are excluded from print.

---

## 🖥️ Run it locally

**The short version:** download the repository and double-click `index.html`.

```text
index.html        – page shell, theme bootstrap
exam.config.js    – pass mark, domains, weights, timer
questions.js      – 180 questions (the whole bank)
diagrams.js       – 8 inline SVG diagrams
app.js            – exam engine
styles.css        – shared theme, light + dark
md-loader.js      – data bootstrap and friendly failure message
```

No `npm install`. No build step. No web server. The page opens from `file://`, reads the bank through a plain `<script>` tag, and starts.

> 💡 **Working in the authoring kit?** `exam-sim/index.html` temporarily loads the shared engine from `../AZ-104/exam-sim/`. Double-click `01-Package-Standalone.bat` once to copy `app.js` and `styles.css` in and rewrite the page to local paths before publishing.

---

## 🧮 Scoring and review

📊 **Scaled score.** `round(correct / total * 1000)` — the same shape Microsoft uses in the score report. Seven out of ten is a pass.

🎆 **Passing feels like passing.** Clearing 700 adds a five-second fireworks overlay to the score report. It is skipped automatically when the operating system asks for reduced motion, and never appears in print.

🔍 **Review everything.** After submitting, filter by all / incorrect / flagged. Each item shows your answer, the correct answer, the full explanation, and the source skill area.

📄 **Print or save.** "Print full review" and "Print score report" produce clean paper layouts with the light palette forced, so a dark-mode session still prints readable black text.

💾 **Resume safe.** An in-progress attempt is saved on every change. Close the tab, come back, and the clock and answers are where you left them.

---

## 🔐 Privacy

Everything is local. The simulator writes four keys to `localStorage` and nothing else:

| Key | Holds |
|---|---|
| `ai901-sim:attempt` | The in-progress attempt, for resume |
| `ai901-sim:settings` | Draw size, timer, instant-feedback preference |
| `ai901-sim:srs` | Spaced-review scheduling data |
| `ai901-sim:theme` | Light or dark choice |

No cookies, no requests to third parties, no telemetry. Clearing site data for the page resets the simulator completely.

---

## ♿ Accessibility

- Full keyboard operation, including `A`–`D` (or `1`–`4`) answer keys and arrow navigation.
- Semantic landmarks, a skip link, and a polite live region for toasts.
- Visible focus rings and readable contrast in both themes.
- `prefers-reduced-motion` disables the fireworks and shortens transitions.
- Diagrams are hidden from assistive technology; every diagram question restates the concept in prose.

---

## ⚠️ Disclaimer

Unofficial study material built from publicly available Microsoft Learn content. Not affiliated with or endorsed by Microsoft. Exam objectives and product behaviour change; verify the current skills measured on Microsoft Learn before sitting the exam. Facts snapshot: **November 2026**.

<div align="center">

**[▶ Start practising](https://chrismunnps.github.io/exam-sim/ai-901/)** · [Microsoft Learn AI-901](https://learn.microsoft.com/en-us/credentials/certifications/azure-ai-fundamentals/)

</div>
