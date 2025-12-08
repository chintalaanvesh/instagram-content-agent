# instagram-content-agent

Agent that converts top AI news into Instagram-ready posts.

## What it does
- Fetches news from top AI sites
- Scores relevance for your target audience
- Generates hooks, captions, hashtags, overlay text, and image prompts
- Produces images (via image API) and saves public URLs
- Writes final outputs (hooks, captions, hashtags, image URLs, prompts, overlay text) to a Google Sheet

## Repo structure
- `src/` - production code (fetchers, generators, image glue, sheet writer)
- `experiments/` - timestamped run metadata (manifests only, no images)
- `notebooks/` - prototyping notebooks
- `tests/` - unit/integration tests
- `config/` - audience profiles, prompt versions

## Quick start
1. Create a Python virtual env and install deps: `pip install -r requirements.txt`
2. Add service credentials as GitHub repo secrets (do **not** commit them)
3. Run `python src/runner.py` (stub will create a manifest under `experiments/`)

## Notes
- Do not commit secrets or large generated images to Git.
- Store generated images in S3/GCS and include the public/signed URLs in manifests.
