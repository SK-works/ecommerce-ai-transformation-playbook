# Week 3 — AI Knowledge Assistant (RAG Chatbot)
## A Deployed RAG Chatbot for eCommerce Content Operations

**Project:** eCommerce AI Transformation Playbook  
**Author:** Sravanthi | Lead Specialist, AI Transformation & Strategic Projects  
**Date:** June 2026  
**Live Demo:** [Open the eCommerce AI Assistant](https://cdn.botpress.cloud/webchat/v3.6/shareable.html?configUrl=https://files.bpcontent.cloud/2026/06/29/10/20260629101945-GGRHALLO.json)

---

## What This Is

A live, publicly accessible RAG (Retrieval-Augmented Generation) chatbot that answers eCommerce content operations questions — grounded in a structured 6-document knowledge base covering product description standards, taxonomy rules, image compliance, content quality, terminology, and attribute extraction.

Anyone can open the link, ask a question, and get a grounded, accurate answer drawn directly from the knowledge base.

---

## The Problem It Solves

eCommerce content teams deal with a high volume of repetitive questions:
- "How long should a product description be?"
- "Where do I classify an electric hand blender?"
- "What images are required for a fashion listing?"
- "What does A+ content mean?"
- "Which attributes are mandatory for instant coffee?"

Without a knowledge system, these questions are answered inconsistently — by asking a senior team member, searching through scattered documents, or guessing. This creates quality variability, slows onboarding, and wastes senior team time on questions that have clear, documented answers.

The eCommerce AI Assistant solves this by making the knowledge instantly accessible to anyone on the team, at any time.

---

## Architecture

```
User Question
      ↓
  Botpress Chat Interface
      ↓
  RAG Pipeline
  ├── Query is embedded
  ├── Semantic search across knowledge base
  └── Relevant chunks retrieved
      ↓
  LLM generates answer grounded in retrieved content
      ↓
  Response returned to user
```

**Technology stack:**
- **Platform:** Botpress (browser-based, no infrastructure required)
- **RAG engine:** Built-in Botpress knowledge base with semantic search
- **LLM:** GPT-4o (via Botpress)
- **Knowledge base:** 6 custom documents (plain text, structured content)
- **Deployment:** Cloud-hosted, publicly accessible via shareable link

---

## The Knowledge Base

Six documents covering the core knowledge an eCommerce content team needs:

| # | Document | What It Covers |
|---|---|---|
| 01 | Product Description Style Guide | Structure, tone, word counts, common errors, quality checklist |
| 02 | Product Taxonomy Guide | 10 top-level categories with definitions, subcategories, classification rules |
| 03 | Image Compliance Checklist | Technical specs, content standards, category-specific image requirements |
| 04 | Content Quality Checklist | 5 quality dimensions, title formula, bullet point standards, quality tiers |
| 05 | eCommerce Glossary | 25+ terms from A+ content to waterfall content strategy |
| 06 | Attribute Extraction Guide | Mandatory attributes by category, extraction process, common errors |

All knowledge base documents are in the `/knowledge-base` folder of this repository.

---

## Sample Questions and Answers

**Q: What makes a good product description?**  
The assistant returns the four-component structure (opening line, feature narrative, use case anchor, closing line), tone guidelines, word count standards, and a quality checklist — all drawn from Document 01.

**Q: Where should I classify an electric hand blender?**  
The assistant correctly identifies Home and Kitchen → Kitchen Appliances, applying the primary use classification rule from Document 02.

**Q: What images are required for a fashion listing?**  
The assistant returns the full image sequence: hero image specs, on-model requirement, close-up of fabric, variant image rules, and the compliance checklist — from Document 03.

---

## Business Impact

| Metric | Manual Process | With AI Assistant |
|---|---|---|
| Time to answer a content standards question | 5–15 mins (find doc, search, read) | Under 30 seconds |
| Consistency of answers across team | Variable (depends on who answers) | Consistent (single source of truth) |
| Availability | Business hours only | 24/7 |
| Onboarding time for new content writers | 2–3 days to absorb standards | Same-day self-serve access |

---

## Live Demo

**Try it here:** [eCommerce AI Assistant](https://cdn.botpress.cloud/webchat/v3.6/shareable.html?configUrl=https://files.bpcontent.cloud/2026/06/29/10/20260629101945-GGRHALLO.json)

Suggested test questions:
- "What is the word count for a standard product description?"
- "What attributes are mandatory for instant coffee listings?"
- "What is a ghost mannequin?"
- "What is the difference between a SKU and a variant?"
- "What makes a listing retail ready?"
- "Where do I classify a children's tablet?"

---

## What I Learned

**RAG works best when the knowledge base is well-structured.** The quality of the chatbot's answers is directly proportional to the quality of the documents behind it. Clear headings, explicit rules, and concrete examples in the source documents produce specific, actionable answers. Vague source documents produce vague answers — the LLM cannot invent precision that isn't in the knowledge base.

**System prompts matter.** Constraining the bot to eCommerce content operations topics only — and instructing it to reference the knowledge base rather than general knowledge — significantly improved answer accuracy and relevance.

**Browser-based RAG tools have closed the gap with custom-built pipelines** for portfolio and proof-of-concept purposes. Botpress delivered a production-quality chatbot experience without requiring infrastructure setup, vector database configuration, or embedding model selection — decisions that matter at enterprise scale but create unnecessary friction for demonstration projects.

**At enterprise scale, this architecture would look different:** a dedicated vector database (Supabase with pgvector or Pinecone), a custom embedding model, retrieval pipeline tuning, and integration with internal knowledge systems (Confluence, SharePoint, Google Drive). The Botpress deployment demonstrates the concept and output — the enterprise version would require an engineering team and a formal knowledge management strategy.

---

## Files in This Folder

```
week3-knowledge-assistant/
├── README.md (this file)
└── knowledge-base/
    ├── kb_01_product_description_style_guide.txt
    ├── kb_02_product_taxonomy_guide.txt
    ├── kb_03_image_compliance_checklist.txt
    ├── kb_04_content_quality_checklist.txt
    ├── kb_05_ecommerce_glossary.txt
    └── kb_06_attribute_extraction_guide.txt
```

---

[← Week 2 — eCommerce Prompt Library](../week2-prompt-library/README.md) | [Week 4 — Product Brief Automation Workflow →](../week4-automation-workflow/README.md)

*Built as part of the eCommerce AI Transformation Playbook — a 6-week hands-on AI learning and deployment project.*
