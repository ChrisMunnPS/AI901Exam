# AI-901 cheat sheet 4/5 — Natural language processing on Azure

*One page. Facts snapshot 2026-11; verify current behaviour on Microsoft Learn before the exam.*

## Typical NLP flow

```text
Input text → language detection → sentiment / key phrases / entities → structured output
```

Language detection usually runs first so later models know which language rules and models to apply.

## Azure AI Language

| Capability | What it returns |
|---|---|
| **Language detection** | Detected language and a confidence score |
| **Sentiment analysis** | Positive, negative, neutral, or mixed, with confidence scores; optionally per sentence |
| **Opinion mining** | Sentiment tied to specific aspects or targets in the text |
| **Key phrase extraction** | The main concepts and terms |
| **Named entity recognition (NER)** | Typed entities: person, organisation, location, date, quantity |
| **PII detection** | Personal data found, with optional redaction |
| **Summarisation** | A short version of long text, including conversations |
| **Question answering** | The best answer from a curated knowledge base, with confidence |
| **Conversational language understanding (CLU)** | The predicted intent and extracted entities |

**Language Studio** is a browser playground for testing these features without code.

## Sentiment and opinions

| Term | Meaning |
|---|---|
| **Document sentiment** | Overall label and confidence for the whole text |
| **Sentence sentiment** | A label per sentence, so one negative paragraph does not hide the rest |
| **Opinion mining** | Links an opinion to its target: location positive, room service negative |

**Exam trap:** sentiment tells you *how* someone feels; opinion mining tells you *what* they feel it about.

## Named entities vs key phrases

| | Named entity recognition | Key phrase extraction |
|---|---|---|
| **Output** | Typed entities with categories | Important terms and phrases |
| **Example** | Person: Ada Lovelace; Location: Paris; Date: 12 May | "supplier contract", "delivery delay" |
| **Use** | Extract people, places, organisations, dates | Index, search, topic review |

**PII detection** is a specialised entity task: it finds names, phone numbers, addresses, and other personal data, and can return redacted text.

## Summarisation

| Type | How it works | Trade-off |
|---|---|---|
| **Extractive** | Selects the most important existing sentences | Faithful wording, but can be disjointed |
| **Abstractive** | Generates new wording that captures the meaning | Fluent, but must be checked for accuracy |
| **Conversation summarisation** | Summarises a dialogue into issues, resolution, and follow-ups | Built for support transcripts |

## Question answering vs CLU

| | Question answering | Conversational language understanding |
|---|---|---|
| **Purpose** | Retrieve an answer from curated content | Decide what the user wants to do |
| **Input** | A question | An utterance |
| **Output** | Answer text, source, confidence | Intent and entities |
| **Built from** | FAQs, documents, URLs | Labelled utterances |
| **Example** | "What is the returns window?" → 30 days | "Cancel my order" → CancelOrder, order id |

**Exam trap:** predictable FAQ-style answers point to question answering. A bot that must choose an action points to CLU.

## CLU concepts

| Term | Meaning | Example |
|---|---|---|
| **Intent** | The user's goal or action | BookFlight, CancelBooking, Complain |
| **Entity** | A detail that fills in the intent | Destination: Paris; Date: Friday |
| **Utterance** | A labelled example phrase used for training | "I need a flight to Paris on Friday" |

More varied, correctly labelled utterances produce a more robust model.

## Translation and speech

| Capability | What it does |
|---|---|
| **Text translation** | Converts text between languages; can auto-detect the source |
| **Document translation** | Translates whole documents while preserving structure |
| **Custom glossary** | Forces brand or domain terms to translate consistently |
| **Speech to text** | Transcribes spoken audio |
| **Text to speech** | Synthesises spoken audio from text |
| **Speech translation** | Recognises speech in one language and outputs another, as text or speech |

**Exam trap:** language detection **identifies** the language; translation **converts** it. Speech recognition converts audio to text; speech synthesis does the reverse.

## Choosing a service

| Requirement | Capability |
|---|---|
| Is this review positive or negative? | Sentiment analysis |
| Which product does the customer mention? | Named entity recognition |
| What is this document about? | Key phrase extraction |
| Which language is this? | Language detection |
| Hide names before sharing | PII detection and redaction |
| Summarise a long call transcript | Summarisation |
| Answer FAQs from a knowledge base | Question answering |
| Decide book versus cancel | CLU intent recognition |
| Translate into 12 languages | Azure AI Translator |
| Voice in French, voice out in English | Speech translation |

## Exam traps

- **Question answering retrieves; CLU classifies intent.** They solve different problems and are often combined.
- **Intent is the goal; entities are the details.**
- **Key phrases are topics; entities are typed things.**
- **PII detection is about privacy, not topic discovery.**
- **Extractive summarisation copies sentences; abstractive writes new ones.**
- **Azure AI Language analyses text; Azure OpenAI generates text.** A summarisation requirement can be met by either, but the exam expects the prebuilt Language feature unless the scenario asks for generative output.
