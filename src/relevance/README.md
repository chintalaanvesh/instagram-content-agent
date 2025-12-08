# n8n relevance workflow

This JSON is the n8n workflow that scores and ranks incoming articles using an LLM.
Import into n8n (Workflows → Import) and re-link credentials after import.

Notes:
- Requires an OpenAI credential named in n8n (anvesh-openai).
- Outputs fields: relevance, virality, recency_score, final_score.
- Version: v1 (2025-12-08)
