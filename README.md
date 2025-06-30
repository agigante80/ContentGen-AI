# ContentGen-AI
Python toolkit that automates SEO-optimized blog and affiliate content generation. 
Utilizing OpenAI's API, it creates engaging topics, articles, and images while managing workflows with CSV files and integrating Telegram notifications and IndexNow. Fully configurable, it adapts to different websites through environment variables and config file.

This project has been generated as a personal playground for me to explore and learn AI technologies and integrations. Feel free to use the script as/if needed; it has been published under the MIT license, so please follow its terms.

Production examples can be found in the following GitHub repositories:  
- https://github.com/agigante80/OndaHertz_es (website: https://www.ondahertz.es/)  
- https://github.com/agigante80/galena_es (website: https://www.galena.es/)

## Overview

The `generate_article.py` script is a central component of the ContentGen-AI toolkit. Its main purpose is to fully automate the creation of SEO-optimized articles and affiliate content, including their images, using OpenAI’s APIs. It manages the entire workflow: from topic selection, content and image generation, file management, notifications, and even search engine indexing.

This script is especially valuable for bloggers, affiliate marketers, and website administrators who want to streamline and scale up their content production with minimal manual intervention.

---

## What Does the Script Do?

### 1. **Environment and Configuration**
- Loads all necessary configuration from environment variables and a shared config file (`config.py`).
- Checks and validates the existence of required directories and CSV files for topics and articles.

### 2. **Topic Management**
- Reads the next topic or affiliate item from a CSV-based queue (`AI_content/list_of_NEW_topics.csv`).
- If the queue is empty, it auto-generates new topics via OpenAI, saves them to the CSV, and sends a Telegram notification.

### 3. **Content Generation**
- **Affiliate Content:** 
  - If the next item is an affiliate product, it reads the associated product info and image, generates a topic and description using OpenAI, and organizes assets.
- **Blog Articles:**
  - If the next item is a standard blog topic, it uses OpenAI to generate a detailed, SEO-optimized article based on the topic and description.

### 4. **Image Generation**
- For standard articles, it generates a relevant image with OpenAI DALL·E, downloads and resizes it, and saves it in the specified directory.
- Generates descriptive alt text for every image using OpenAI, further boosting accessibility and SEO.

### 5. **Article Saving**
- Saves generated articles as Markdown files, placing them in the correct directory.
- Handles file naming and category-based paths for better organization.

### 6. **Notifications & Indexing**
- Sends progress and error notifications via Telegram at key workflow stages.
- Notifies multiple IndexNow endpoints to accelerate search engine indexing of the new article.

### 7. **CSV Workflow Management**
- Moves processed topics to archive CSVs.
- Handles invalid or error-prone topics by logging and moving them to an error CSV, while notifying via Telegram.

---

## Pros & Advantages

- **End-to-End Automation:** Handles everything from topic ideation to publishing-ready content, image management, and indexing.
- **Bulk Workflow Support:** CSV-based queue enables batch processing of topics and affiliate items.
- **Affiliate & Blog Flexibility:** Can handle both standard blog articles and affiliate product content, tailoring prompts and output accordingly.
- **AI-Driven Content:** Uses OpenAI for both content and image generation, ensuring high quality and relevance.
- **SEO Optimization:** Built-in prompt engineering and metadata handling for SEO-friendly articles and images.
- **Error Handling & Logging:** Robust logging, notification, and error recovery mechanisms for reliability.
- **Search Engine Indexing:** Fast, automated submission to search engines via IndexNow.
- **Configurable & Portable:** Adaptable to different sites via environment variables and config files; easy to integrate in various content pipelines.
- **Team Notifications:** Telegram integration keeps you and your team in the loop about workflow progress and issues.
- **Accessible Images:** Automatic alt text generation improves accessibility and SEO compliance.

---

## Usage

1. **Set up environment variables and `config.py`** with your API keys and site details.
2. **Prepare your topics** in the CSV, or let the script auto-generate them.
3. **Run the script:**  
   ```bash
   python AI_scripts/generate_article.py
   ```
4. **Monitor progress** via logs and Telegram notifications.
5. **Find your generated articles** (Markdown files) and images in the configured directories.

---

## Summary

`generate_article.py` is a comprehensive automation script for AI-driven content and image generation, ideal for anyone looking to scale up their content marketing with minimal manual effort. It leverages the latest in AI, integrates with popular messaging and indexing services, and is designed for reliability and flexibility in a modern content pipeline.