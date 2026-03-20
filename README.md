# Instagram Content Agent

> Fully automated pipeline from news discovery to Instagram-ready content. RSS feeds in, polished carousel posts out — no manual intervention required.

![n8n](https://img.shields.io/badge/n8n-EA4B71?logo=n8n&logoColor=white&style=flat-square)
![OpenAI](https://img.shields.io/badge/GPT--4o-412991?logo=openai&logoColor=white&style=flat-square)
![Gemini](https://img.shields.io/badge/Gemini_Imagen_4.0-4285F4?logo=google&logoColor=white&style=flat-square)
![Cloudinary](https://img.shields.io/badge/Cloudinary-3448C5?logo=cloudinary&logoColor=white&style=flat-square)

---

## Pipeline Overview

```
RSS Feeds
   → Relevance & virality scoring (GPT-4o)
   → Top 3 stories selected
   → Caption + hook + hashtag generation
   → Image strategy (slide count, AI vs stock)
   → AI image generation (Gemini Imagen 4.0)
   → Post-processing + text overlay (Cloudinary)
   → Content calendar log (Google Sheets)
```

Runs on a daily schedule or on-demand from within n8n.

---

## Features

**Content Discovery**
- Ingests multiple RSS feeds from tech and AI publications
- Filters articles by recency and normalizes metadata

**LLM Scoring**
- Each article is scored on relevance, virality potential, and recency
- Weighted scoring selects the top 3 stories automatically

**Caption Engine**
- Generates scroll-stopping hooks, 3–4 paragraph captions, and optimized hashtags
- Strict JSON output ensures reliable downstream parsing in n8n

**Image Strategy**
- Decides slide count (1–4) and whether to use AI-generated or stock images per article
- Generates detailed prompts for visual consistency across the carousel

**AI Image Generation**
- Gemini Imagen 4.0 Ultra produces cinematic, Instagram-native visuals
- Each slide prompt is enriched from the article context

**Cloudinary Post-Processing**
- Applies background overlays and mobile-optimized text boxes
- Returns final CDN URLs ready for scheduling

**Content Calendar**
- Appends hook, caption, hashtags, and image URLs to Google Sheets
- Serves as a persistent, searchable content history

---

## Tech Stack

| Component | Technology |
|-----------|------------|
| Orchestration | n8n |
| Text generation & scoring | OpenAI GPT-4o / GPT-4o-mini |
| Image generation | Google Gemini Imagen 4.0 Ultra |
| Image hosting & processing | Cloudinary |
| Content calendar | Google Sheets |
| News source | RSS feeds |

---

## Setup

### Prerequisites

- n8n instance (self-hosted or cloud)
- OpenAI API key
- Google Gemini API key
- Cloudinary account with an unsigned upload preset
- Google Cloud project with Drive and Sheets API enabled

### Credentials

All credentials are managed inside n8n's Credentials Manager. This repository contains no API keys, OAuth tokens, or secrets.

Create the following credentials in n8n before importing workflows:

| Credential | Used By |
|-----------|---------|
| OpenAI API | Scoring and text generation |
| Google Gemini API | Image generation |
| Cloudinary | Image upload and transformation |
| Google Drive OAuth2 | File access |
| Google Sheets OAuth2 | Content calendar logging |

Refer to each module's `CREDENTIALS.md` for field-by-field configuration instructions.

### Installation

1. Clone the repository:

```bash
git clone https://github.com/chintalaanvesh/instagram-content-agent.git
cd instagram-content-agent
```

2. Import each workflow JSON from `src/` into n8n via **Workflows → Import from File**.

3. Reconnect credentials in each imported workflow.

4. Configure your Google Sheet with the following column headers:
   `Index` · `Hook` · `Captions` · `Hashtags` · `Image 1`

5. Activate the workflow or run it manually via **Execute Workflow**.

---

## Roadmap

- [ ] Direct Instagram posting via Graph API
- [ ] Cross-posting to LinkedIn and X
- [ ] Analytics dashboard (reach, saves, CTR)
- [ ] A/B testing for hooks and visuals
- [ ] Multi-language content generation
- [ ] Persona-based fine-tuning for higher engagement

---

## License

MIT License. See [LICENSE](LICENSE) for details.
