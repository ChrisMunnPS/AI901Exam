# AI-901 cheat sheet 1/5 — AI workloads and responsible AI

*One page. Facts snapshot 2026-11; verify current behaviour on Microsoft Learn before the exam.*

## The family tree

| Term | Definition | Remember |
|---|---|---|
| **Artificial intelligence (AI)** | Systems that perform tasks that normally need human intelligence: reasoning, perception, language, learning. | The umbrella term |
| **Machine learning (ML)** | Models learn patterns from data instead of following hand-written rules. | Learns from examples |
| **Deep learning** | ML using neural networks with many hidden layers. | ML + deep neural networks |
| **Generative AI** | Models that create new content — text, images, audio, code — from a prompt. | Creates, not just classifies |
| **Agent** | A language model plus instructions plus tools, able to plan and act. | Model + instructions + tools |

**Exam trap:** generative AI is one application of AI, not a synonym for it. Vision, speech, and language services are separate workloads.

## AI workloads

| Workload | What it does | Example |
|---|---|---|
| **Computer vision** | Interprets images and video: classify, detect, read text, describe. | Shelf audit, defect detection |
| **Natural language processing (NLP)** | Extracts meaning from text: sentiment, entities, key phrases, summaries. | Route support email |
| **Speech** | Converts audio to text, text to audio, or speech between languages. | Voice assistant, captions |
| **Conversational AI** | Holds a dialogue through a bot or agent. | Support chatbot |
| **Predictive analytics** | Forecasts future numeric outcomes from history. | Next month's revenue |
| **Recommendation** | Suggests items from user and item behaviour. | "Customers also bought" |
| **Anomaly detection** | Finds observations that differ from normal. | Fraud, equipment failure |
| **Information extraction** | Turns documents into structured fields. | Invoice number and total |

## Machine learning task types

| Task | Output | Label needed? | Example |
|---|---|---|---|
| **Classification** | A class or category | Yes, supervised | Spam / not spam |
| **Regression** | A continuous number | Yes, supervised | House price |
| **Forecasting** | A future number from a time series | Yes, supervised | Electricity demand |
| **Clustering** | Groups of similar records | No, unsupervised | Customer segments |
| **Anomaly detection** | Unusual records | Usually no | Unusual transaction |

**Decision rule:** a named category means classification; a quantity means regression; future time-ordered values mean forecasting; no labels and "find groups" means clustering.

## Computer vision scenarios

| Scenario | Task |
|---|---|
| One label for the whole image | Image classification |
| A label and a bounding box per object | Object detection |
| Text read from a photo or scan | Optical character recognition (OCR) |
| Fields such as vendor and total from a form | Document Intelligence |
| Whether a face exists, and its pose or blur | Face detection |
| Who a face belongs to | Face recognition (Limited Access) |

## Responsible AI

| Principle | What it demands | Typical control |
|---|---|---|
| **Fairness** | Treat people equitably; avoid bias and discrimination. | Test outcomes across groups, balanced data |
| **Reliability and safety** | Operate predictably and fail safely. | Confidence thresholds, fallbacks, testing |
| **Privacy and security** | Protect personal and organisational data. | Encryption, access control, PII redaction |
| **Inclusiveness** | Be usable by as many people as possible. | Captions, translation, accessibility |
| **Transparency** | Be open about AI use, behaviour, and limits. | Disclosures, explanations, documentation |
| **Accountability** | People remain answerable for the system. | Ownership, review boards, audit records |

**Exam trap:** unequal outcomes for similar people is **fairness**. Telling users an AI made the decision is **transparency**. Owning and governing the system is **accountability**. Accessibility is **inclusiveness**.

## Matching requirements to workloads

| Requirement keyword | Workload |
|---|---|
| Image, photo, video, camera, shelf | Computer vision |
| Review, email, contract, text, language | NLP |
| Audio, voice, transcription, captions | Speech |
| Chat, bot, dialogue, self-service | Conversational AI |
| Forecast, demand, next month, revenue | Predictive analytics |
| "Customers also bought", personalise | Recommendation |
| Unusual, outlier, fraud, deviation | Anomaly detection |

## Exam traps

- **ML vs deep learning:** all deep learning is ML, but not all ML is deep learning.
- **Classification vs regression:** two classes or five classes are both classification; price, demand, and temperature are regression.
- **Classification vs object detection:** detection also answers *where*, with a bounding box.
- **Speech recognition vs synthesis:** recognition is audio → text; synthesis is text → audio.
- **Responsible AI is six principles, not one.** A scenario about bias is fairness; a scenario about disclosure is transparency.
- **Content filters and prompt shields** are generative-AI safety controls, not an AI workload.
