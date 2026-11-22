# AI-901 cheat sheet 5/5 — Generative AI on Azure

*One page. Facts snapshot 2026-11; verify current behaviour on Microsoft Learn before the exam.*

## Core terms

| Term | Meaning |
|---|---|
| **Foundation model** | Large model pretrained on broad data, adaptable to many tasks. |
| **Large language model (LLM)** | Foundation model trained to predict and generate token sequences. |
| **Small language model (SLM)** | Fewer parameters, focused tasks, local or edge deployment. |
| **Token** | Unit of text: a word, part of a word, or punctuation. Cost and context use tokens. |
| **Context window** | Maximum input plus output tokens considered at once. |
| **Inference** | Using a trained model to generate a response; weights do not change. |
| **Deployment** | A named hosted instance of a model, called through an endpoint. |

## Anatomy of a request

```text
System prompt (role, rules) + User prompt (request) + Grounding data
        ↓
   Language model → completion
```

The system prompt sets behaviour and constraints, the user prompt carries the request, and grounding data supplies evidence. Earlier assistant messages can be replayed as history.

## Prompting techniques

| Technique | What you do and when |
|---|---|
| **Zero-shot** | Ask with no examples; simple, well-known task. |
| **Few-shot** | Include a few worked examples; output format matters. |
| **Role prompting** | Give the model a role in the system prompt; tone and expertise. |
| **Format instruction** | Ask for JSON, a table, or a length limit; downstream parsing. |
| **Grounding** | Supply source text and require the answer to use it; current or private facts. |

**Prompt engineering changes the request, not the model weights.** Try it before paying for fine-tuning.

## Generation settings

| Setting | Effect and typical choice |
|---|---|
| **Temperature** | Higher is more random and creative; lower is focused and repeatable. Low for facts. |
| **Top-p (nucleus)** | Considers the smallest token set whose cumulative probability reaches p. Tune one at a time. |
| **Max output tokens** | Caps completion length; controls cost and truncation. |

## Azure OpenAI and Foundry

| Component | Purpose |
|---|---|
| **Azure OpenAI in Foundry Models** | OpenAI models with Azure identity, networking, content filtering, compliance. |
| **Microsoft Foundry** | Model catalogue, playgrounds, deployments, evaluations, agents, governance. |
| **Deployment** | Host a chosen model with a name and capacity. |
| **Endpoint and key or managed identity** | How an application authenticates and calls the deployment. |
| **Evaluation** | Measure quality, groundedness, relevance, and safety before release. |

**Exam trap:** Azure OpenAI hosts generative models with Azure controls. Azure AI Language, Vision, and Speech are prebuilt task services. Azure Machine Learning trains custom classical models.

## RAG — retrieval-augmented generation

```text
User question → retrieve relevant chunks → add to prompt → model answers → citations
```

| Step | Typical service and why |
|---|---|
| **Index** | Azure AI Search. Keyword, vector, or hybrid search over your content. |
| **Retrieve** | Azure AI Search query. Fetch the most relevant chunks. |
| **Augment** | Prompt construction. Put evidence and instructions in the context window. |
| **Generate** | Azure OpenAI deployment. Answer using the supplied evidence. |
| **Cite** | Application. Let users verify the answer against sources. |

RAG reduces hallucinations but does not guarantee truth. Use it for "answer from our documents" and knowledge that changes often.

## Hallucination, grounding, and citations

| Term | Meaning |
|---|---|
| **Hallucination** | Fluent, confident output that is false or unsupported. |
| **Grounding** | Supplying source evidence so the answer is based on it. |
| **Citation** | A link from a claim back to the retrieved source. |

Reduce hallucination with retrieval, a strict instruction to use only supplied sources, citations, lower temperature, and human review for high-impact decisions.

## Prompting vs RAG vs fine-tuning

| Approach | Changes, best for, cost |
|---|---|
| **Prompt engineering** | Changes the request. Tone, format, quick iteration. Lowest cost. |
| **RAG** | Changes context at query time. Current or private facts, citations. Medium. |
| **Fine-tuning** | Changes model weights with examples. Consistent style or narrow task. Highest. |

**Fine-tuning teaches behaviour and format; RAG supplies knowledge.** If facts change weekly, use RAG.

## Responsible generative AI

| Control | What it does |
|---|---|
| **Content filters** | Assess prompts and completions for hate, sexual, violence, and self-harm, with severity thresholds. |
| **Prompt shields** | Detect jailbreaks and indirect prompt injection, including hidden document instructions. |
| **Human oversight** | Review outputs before high-impact decisions such as hiring, credit, or healthcare. |
| **Evaluation and monitoring** | Test quality, safety, and groundedness before release, then watch production traffic. |

**Exam trap:** content filters handle harmful content; prompt shields handle prompt attacks. Neither replaces human review.

## Copilot and agents

| Concept | What it is |
|---|---|
| **Microsoft 365 Copilot** | Assistant in Word, Excel, Outlook, and Teams; uses content the user can already access. |
| **Copilot Studio** | Low-code builder for custom copilots and agents: topics, connectors, knowledge. |
| **Agent** | A language model plus instructions plus tools. |
| **Tools** | Knowledge tools retrieve; action tools send mail or update a record. |

## Exam traps

- **Tokens are text units**, not credentials or pixels.
- **A bigger context window does not make output true.**
- **Higher temperature increases variety, not safety.**
- **RAG grounds answers; fine-tuning changes behaviour.**
- **Citations make answers verifiable; they do not prove them.**
