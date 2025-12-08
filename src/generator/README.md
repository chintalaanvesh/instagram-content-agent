# n8n generator workflow

This folder contains the n8n workflow that
- Generates Hook, caption, and hashtags for each selected article
- Decides number of images and overlay text
- Generates detailed image prompts for each overlay text

Files
- `n8n_generator_v1_2025-12-08.json` — main generator pipeline (v1)

Import
1. In n8n, go to Workflows → Import.
2. Select this JSON file.
3. Re-link the `anvesh-openai` OpenAI credential inside n8n (API key is NOT stored in this file).
