# Credentials & config for Sheets workflow

This workflow requires the following n8n credentials (create these inside n8n credential manager):

- Google Drive OAuth: credential name used in workflow = "anvdrv-musn8n"
- Google Sheets OAuth: credential name used in workflow = "Google Sheets account"

Replace placeholders in the workflow JSON:
- folderId -> actual Drive folder ID
- documentId -> actual Sheets document ID

Important:
- Do NOT store actual OAuth client secrets or service account JSON in this repository.
- If you use a service account, create the account and add it to the Drive folder or share the sheet appropriately.
