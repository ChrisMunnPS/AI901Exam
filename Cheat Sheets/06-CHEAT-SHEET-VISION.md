# AI-901 cheat sheet 3/5 — Computer vision on Azure

*One page. Facts snapshot 2026-11; verify current behaviour on Microsoft Learn before the exam.*

## Azure AI Vision

| Capability | Output |
|---|---|
| **Caption** | One natural-language sentence for the whole image |
| **Dense captions** | Several captions, each tied to a region of the image |
| **Tags** | Keywords such as outdoors, person, building |
| **Objects** | A label and a bounding box for each object |
| **Read (OCR)** | Printed and handwritten text as lines and words, with positions |
| **Smart cropping** | Crop coordinates that keep the main subject visible |
| **People detection** | Locations of people in the image |

**Vision Studio** is a browser playground for trying these features on sample or uploaded images without writing code.

## Image classification vs object detection

| | Image classification | Object detection |
|---|---|---|
| **Question** | What is in the image? | What is where? |
| **Output** | One or more labels for the whole image | A label **and** a bounding box per object |
| **Multiple objects** | Not located | Each object reported separately |
| **Example** | Photo contains a dog | Dog at (x1, y1, x2, y2), cat at (x3, y3, x4, y4) |

**Exam trap:** if the requirement mentions *position*, *count*, or *multiple items in one image*, choose object detection.

## OCR vs Document Intelligence

| | OCR (Azure AI Vision Read) | Document Intelligence |
|---|---|---|
| **Input** | Photo, sign, scan, page | Forms, invoices, receipts, IDs |
| **Output** | Text and word positions | Structured fields, tables, key-value pairs |
| **Understands layout** | Limited to lines and words | Yes: sections, tables, selection marks |
| **Best for** | Unstructured text in an image | Business documents with a known schema |

**Exam trap:** OCR gives you *text*. Document Intelligence gives you *meaning*: which number is the total, which date is due.

## Document Intelligence models

| Model | Extracts |
|---|---|
| **Read** | Text, lines, words, languages |
| **Layout** | Text, tables, selection marks, headers, reading order |
| **Invoice** | Vendor, customer, invoice date, due date, line items, subtotal, tax, total |
| **Receipt** | Merchant, transaction date and time, line items, tax, total |
| **Identity document** | Name, date of birth, document number, expiry from passports and ID cards |
| **Business card** | Name, company, phone, email, address |
| **Custom template** | Your fields from consistent forms |
| **Custom neural** | Your fields from forms with more layout variation |
| **Custom composed** | A collection of models, routed automatically |

**Choose custom** when the prebuilt model's schema does not match your document.

## Custom Vision

| Project type | Output | Label work |
|---|---|---|
| **Image classification** | One or more labels for the whole image | Tag each image |
| **Object detection** | A label and bounding box per object | Draw a box around each object |

Custom Vision is **supervised**: you upload and label your own images, train, evaluate, and publish a prediction endpoint. Use it when the prebuilt models do not cover your classes or objects.

## Face

| Capability | Question it answers |
|---|---|
| **Face detection** | Is there a face, and what is its pose, blur, exposure, or occlusion? |
| **Face verification** | Does this face match the one claimed person? (one-to-one) |
| **Face identification** | Which person in a group matches this face? (one-to-many) |
| **Liveness detection** | Is a real person present, rather than a photo, video, or mask? |

**Limited Access:** identification and verification require approval and responsible AI safeguards. Detection is broadly available. Face recognition is not the same as detection.

## Choosing a service

| Requirement | Service or task |
|---|---|
| Describe a photo, tag it, crop a thumbnail | Azure AI Vision image analysis |
| Read text from a sign or scanned page | Azure AI Vision Read (OCR) |
| Extract fields from invoices or receipts | Document Intelligence prebuilt model |
| Extract fields from your own form layout | Document Intelligence custom model |
| Classify your product photos into categories | Custom Vision image classification |
| Find and locate products or defects in a photo | Custom Vision object detection |
| Detect whether a face is present | Face detection |
| Prevent photo spoofing in face sign-in | Liveness detection |

## Exam traps

- **Azure AI Vision is prebuilt; Custom Vision is trained on your labelled images.**
- **Document Intelligence is built on OCR but adds structure.** Layout is not the same as the invoice model.
- **Bounding boxes mean detection**, not classification.
- **Face detection does not identify anyone.**
- **Smart cropping suggests a crop; it does not remove objects.**
- **Vision Studio is a playground, not a production endpoint.**
