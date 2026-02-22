# 🚀 ReelSync: AI-Powered Social Curation Pipeline

![Hackathon Submission](https://img.shields.io/badge/Hackathon-Submission-blue?style=for-the-badge&logo=hackaday)
![n8n](https://img.shields.io/badge/n8n-FF6D5A?style=for-the-badge&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Airtable](https://img.shields.io/badge/Airtable-18BFFF?style=for-the-badge&logo=airtable&logoColor=white)

An end-to-end, fully automated backend pipeline that scrapes Instagram Reels, uses AI to categorize the vibe, and seamlessly pushes the data to a live, searchable public dashboard. 

## 🔗 Important Links

* **🌐 Live Dashboard:** [View the Softr App](https://linnea14161.softr.app)
* **📺 Video Demo:** [Watch the Pipeline in Action](https://youtu.be/QzQYpOnwJXk)

---

## 🎥 Project Demo

Click the image below to watch the full end-to-end video demonstration of the project:

[![ReelSync Demo](https://img.youtube.com/vi/QzQYpOnwJXk/maxresdefault.jpg)](https://youtu.be/QzQYpOnwJXk)

---

## 🛠️ The Architecture & Tech Stack

This project was built using a robust low-code architecture to ensure maximum speed, reliability, and scalability.

1. **Trigger / Input:** `WhatsApp Bot` 
   * Users text an Instagram Reel link to the bot.
2. **Data Extraction:** `RapidAPI (Instagram Scraper Stable API)` 
   * Extracts the raw JSON metadata and caption directly from the Reel.
3. **AI Processing:** `OpenAI (via n8n LLM Chain)` 
   * Parses the caption, standardizes a 1-word category (e.g., Tech, Travel, Motivation), and generates a 1-sentence vibe summary.
4. **Database:** `Airtable` 
   * Acts as the central brain, securely storing the original URL, AI Category, and Summary.
5. **Frontend UI:** `Softr` 
   * A responsive, Pinterest-style grid board that updates in real-time as new records hit the database.

---

## ⚙️ How It Works (The Pipeline)

> **User Sends Link ➔ Webhook Catches Data ➔ Scraper Pulls Caption ➔ AI Analyzes Text ➔ Airtable Saves Record ➔ Softr Displays Card**

The core logic of this application is handled entirely through **n8n**. The workflow dynamically handles data sanitization (cleaning up messy API header text) and includes intelligent fallbacks (safely labeling videos that do not have captions) to ensure the database never crashes.

---

## 💻 How to Import the Backend

The logic for this application was built using n8n. You can view the exact node structure and API configurations by importing the backend workflow into your own environment.

1. Clone or download this repository.
2. Open your local or cloud instance of **n8n**.
3. Go to your workflows dashboard and click **Import from File**.
4. Select the `.json` file included in this repository.
5. Add your own API credentials (OpenAI, Airtable, RapidAPI) to activate the nodes!

---
