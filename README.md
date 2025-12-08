# 📸 Instagram AI Content Agent  
### **Automated AI-powered Instagram news generation, design & publishing pipeline**

This repository contains an end-to-end automation system that **fetches AI news, ranks it, generates captions, designs carousel images, and logs everything to Google Sheets** — completely automatically.

Built using **n8n**, **OpenAI GPT-4o**, **Google Gemini Imagen**, **Cloudinary**, and **Google Sheets**, it delivers polished Instagram-ready content with zero manual intervention.

---

## 🚀 Features

### 🔍 **1. Automated AI News Fetching**
- Reads RSS feeds from top tech & AI sites  
- Cleans and normalizes article data  
- Filters content based on publication time  

### 🧠 **2. Relevance & Virality Scoring (LLM)**
Each article is evaluated based on:
- **Relevance**  
- **Virality potential**  
- **Recency**  
- Weighted scoring system picks the *top 3* stories of the day  

### ✍️ **3. Caption Generator**
Creates:
- High-converting **Hooks**  
- Scroll-stopping **captions** (3–4 paragraphs)  
- Optimized **hashtags**  

Strict JSON output ensures reliability with n8n workflows.

### 🖼️ **4. Image Strategy Engine**
For each article:
- Decides number of images (1–4)  
- Determines whether to use **AI images** or **stock images**  
- Generates **overlay text** for each slide  

### 🎨 **5. AI Image Generation**
- Uses **Gemini Imagen 4.0 Ultra** to create cinematic, IG-ready assets  
- Converts overlay text into rich, world-class prompts  
- Ensures visual consistency across carousel  

### 🧰 **6. Cloudinary Image Enhancement**
- Adds background overlays  
- Inserts the mobile-optimized text box  
- Creates finalized **Instagram-ready** images  
- Returns CDN URLs  

### 🧾 **7. Google Sheets Content Log**
Automatically appends:
- Hook  
- Caption  
- Hashtags  
- Image URLs  
- Index and tracking metadata  

Functions as your long-term **content calendar**.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **n8n** | Orchestration & workflow automation |
| **OpenAI GPT-4o / GPT-mini** | Relevance scoring + text generation |
| **Google Gemini Imagen 4.0** | AI image generation |
| **Cloudinary** | Image hosting + post-processing |
| **Google Drive & Sheets** | Content storage + logging |
| **RSS Feeds** | Source of AI news |


---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **n8n** | Orchestration & workflow automation |
| **OpenAI GPT-4o / GPT-mini** | Relevance scoring + text generation |
| **Google Gemini Imagen 4.0** | AI image generation |
| **Cloudinary** | Image hosting + post-processing |
| **Google Drive & Sheets** | Content storage + logging |
| **RSS Feeds** | Source of AI news |

---

## 🔐 Security & Credentials

This repository intentionally **does not include**:
- API keys  
- OAuth tokens  
- Service account JSON  
- Secrets  

All sensitive information must be configured inside **n8n Credentials Manager**.

Each module contains its own `CREDENTIALS.md` explaining:
- Required credentials  
- How to configure them after importing workflows  
- What NOT to store in the repo  

⚠️ **Always export n8n workflows WITHOUT credentials.**

---

## 📦 Setup & Installation

### 1️⃣ Clone this repo
```bash
git clone https://github.com/<your-username>/instagram-content-agent.git
cd instagram-content-agent

### 2️⃣ Import workflows into n8n

For each JSON inside `src/*`:

- Open **n8n**
- Go to **Workflows → Import from File**
- Select the JSON workflow
- Reconnect the required credentials

---

### 3️⃣ Connect required credentials in n8n

You will need:

- **OpenAI API credential**
- **Google Gemini API credential**
- **Cloudinary account & preset**
- **Google Drive OAuth**
- **Google Sheets OAuth**

Ensure each credential is created in **n8n Credentials Manager** and matches the credential names used in the workflows.

---

### 4️⃣ Configure Google Sheet

Ensure column names match this schema:

- **Index**
- **Hook**
- **Captions**
- **Hashtags**
- **Image 1**

These fields will be appended automatically during workflow execution.

---

###
The system is scheduled to run daily, but it can also be run manually from inside n8n:

- Open workflow → Click **Execute Workflow**
- Review output in Google Sheets

---

### 🗺️ Roadmap

- [ ] Automatic Instagram posting (Graph API)
- [ ] LinkedIn + X (Twitter) cross-posting
- [ ] Analytics dashboard (reach, CTR, saves)
- [ ] A/B testing for hooks and visuals
- [ ] Multi-language generation
- [ ] Fine-tuned LLM persona for higher CTR

---

### 🤝 Contributing

Contributions are welcome!  
Please open an issue or submit a pull request.

---

### 📄 License

MIT License — free to use, modify, and build upon.


