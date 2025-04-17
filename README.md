# SPL-Localizer

![License](https://img.shields.io/badge/license-MIT-blue)
![Build Status](https://img.shields.io/badge/build-passing-brightgreen)

---

## 📑 Table of Contents

1. [🎯 Project Presentation](#-project-presentation)
2. [🗺️ Plan & Roadmap](#️-plan--roadmap)
3. [✨ Features](#-features)
4. [🏗️ Architecture](#️-architecture)
5. [🚀 Getting Started](#-getting-started)
6. [💡 Usage](#-usage)
7. [⚙️ Configuration](#️-configuration)
8. [🤝 Contributing](#-contributing)
9. [📄 License](#-license)

---

## 🎯 Project Presentation

**SPL-Localizer** is an end-to-end, AI-driven internationalization pipeline designed to automate the extraction, keying, and translation of user-facing text in any web application. By crawling your codebase, identifying localizable strings, generating translation keys, and leveraging OpenAI’s powerful models, AI-Localizer delivers context-aware, high-fidelity translations seamlessly integrated into popular i18n frameworks (e.g., i18next, react-intl).

**Why SPL-Localizer?**
- Eliminate manual string collection and key assignment
- Guarantee consistency and context-aware translations
- Integrate continuous localization into CI/CD workflows
- Scale effortlessly across dozens of languages and millions of lines of code

---

## 🗺️ Plan & Roadmap

| Phase | Goals | Timeline |
|:-----:|:------|:--------:|
| **Phase 1** | Extraction Engine: Crawl code (HTML, JS/TS, templates), detect strings, classify context | Week 1–2 |
| **Phase 2** | Key Management: Deduplicate, cluster similar strings, generate unique keys | Week 3–4 |
| **Phase 3** | Translation Pipeline: Prompt engineering for context-aware translations, bulk API integration | Week 5–7 |
| **Phase 4** | QA & Consistency: Automated glossary/style-guide generation, similarity checks | Week 8–9 |
| **Phase 5** | CI/CD Integration: Incremental updates, fine-tuning for cost optimization | Week 10–12 |

> **Milestones:**
> - Prototype extraction and key generation (end of Week 2)
> - First-pass translation of a demo codebase (end of Week 7)
> - Automated QA suite and glossary export (end of Week 9)
> - CI/CD integration and public alpha release (end of Week 12)

---

## ✨ Features

- **Automatic Extraction**: Detect strings in HTML, React/Vue components, server-side templates.
- **Smart Key Generation**: Cluster similar messages to avoid duplicates, create human-readable keys.
- **Contextual Translation**: Include surrounding code snippets and UI metadata for accurate translations.
- **Glossary & Style Guides**: Auto-generate term lists to maintain consistency.
- **Incremental Updates**: Only new or changed strings are reprocessed in pull requests.
- **Custom Fine-Tuning**: Train a project-specific model to reduce token usage and improve domain accuracy.

---

## 🏗️ Architecture

```plaintext
┌───────────────┐   Crawl & Parse   ┌───────────────┐
│   Codebase    │ ───────────────► │ Extraction    │
│ (HTML, JS/TS, │                   │ Engine        │
│ Templates)    │                   └──────┬────────┘
└───────────────┘                          │
      ▲                                     │
      │     Cluster & Key Generation        ▼
┌───────────────┐                   ┌───────────────┐   Translation   ┌───────────────┐
│  Key Store    │◄──────────────────│   Clustering   │◄────────────── │ OpenAI Models │
└───────────────┘    Embeddings     │ & Key Gen     │   API Calls     └───────────────┘
                                           │
                                           ▼
                                 ┌──────────────────┐
                                 │ QA & Glossary    │
                                 └──────────────────┘
                                           │
                                           ▼
                                 ┌──────────────────┐
                                 │ CI/CD Integration│
                                 └──────────────────┘
```

*Happy Translating!*

