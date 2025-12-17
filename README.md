# 🌐 Universal Website Scraper

A **Universal Website Scraper** built to extract structured, section-aware content from **any website** — including **static pages and JavaScript-rendered sites**.  
It returns clean **JSON output** and provides a **simple frontend viewer** to explore and download the scraped data.

This project was built as an **MVP Full-Stack Assignment** focusing on robustness, clarity, and real-world scraping scenarios.

---

## 🚀 Features

- 🔍 Scrapes **static & JS-rendered websites**
- 🧠 **Automatic fallback** from static scraping → Playwright rendering
- 🖱️ Handles **click flows** (tabs, “Load more”, show more buttons)
- 📜 Supports **scrolling & pagination** (depth ≥ 3)
- 🧩 Groups content into **logical sections** (Hero, Nav, Footer, FAQ, etc.)
- 📦 Outputs **section-aware structured JSON**
- 🖥️ Minimal **frontend UI** to:
  - Input URL
  - View parsed sections
  - Expand JSON per section
  - Download full JSON result
- 🛡️ Graceful error handling with partial results

---

## 🛠️ Tech Stack

### Backend
- **Python 3.10+**
- **FastAPI**
- **httpx / requests**
- **BeautifulSoup / lxml**
- **Playwright (Python)** – for JS rendering
- **Uvicorn**

### Frontend
- Minimal HTML / Jinja2 based UI  
- JSON viewer with expandable sections

---

## 📂 Project Structure

```bash
Universal_Website_Scraper/
│
├── app/ # Backend source code
├── templates/ # Frontend templates
├── static/ # UI assets (if any)
├── run.sh # One-command run script
├── requirements.txt # Dependencies
├── README.md # Project documentation
├── design_notes.md # Design & strategy explanation
├── capabilities.json # Implemented feature checklist
└── main.py # Application entry point
```

---
