# Universal Website Scraper 🚀

**Universal Website Scraper** is a full-stack web scraping solution designed to extract clean, structured, and section-aware content from any website — whether it’s static HTML or JavaScript-rendered. The project provides both a powerful backend API and a minimal frontend viewer so users can explore and download scraped results as structured JSON. :contentReference[oaicite:0]{index=0}

---

## 🧠 Features

✔ Scrapes both **static and JavaScript-rendered websites**  
✔ Automatic fallback from static scraping to Playwright rendering  
✔ Handles interactive flows (e.g., click “Load more”, navigation tabs)  
✔ Supports scrolling and pagination (deep scraping with depth ≥ 3)  
✔ Outputs **section-aware structured JSON**  
✔ Includes a **simple UI** to input URLs, view parsed sections, and download results  
✔ Robust error handling with partial result recovery :contentReference[oaicite:1]{index=1}

---

## 🧱 Tech Stack

### Backend
- **Python 3.10+**
- **FastAPI** – REST API framework  
- **httpx / requests** – HTTP client  
- **BeautifulSoup / lxml** – Parsing HTML  
- **Playwright (Python)** – Browser automation for dynamic pages  
- **Uvicorn** – ASGI server  

### Frontend
- Minimal **HTML + Jinja2** UI  
- JSON viewer for exploring scraped data :contentReference[oaicite:2]{index=2}

---

## 📂 Project Structure

```bash
Universal_Website_Scraper/
│
├── backend/
│   ├── app/
│   │   ├── __init__.py
│   │   │
│   │   ├── main.py                  # FastAPI app entry point
│   │   ├── config.py                # App configuration & constants
│   │   │
│   │   ├── api/                     # API routes
│   │   │   ├── __init__.py
│   │   │   └── scraper_routes.py    # Scraping endpoints
│   │   │
│   │   ├── core/                    # Core scraping logic
│   │   │   ├── __init__.py
│   │   │   ├── static_scraper.py    # Static HTML scraping
│   │   │   ├── dynamic_scraper.py   # Playwright-based scraping
│   │   │   ├── interaction.py       # Scroll, click, pagination handling
│   │   │   └── fallback.py          # Static → Dynamic fallback logic
│   │   │
│   │   ├── services/                # Business logic layer
│   │   │   ├── __init__.py
│   │   │   └── scraper_service.py   # Orchestrates full scraping flow
│   │   │
│   │   ├── schemas/                 # Request/response models
│   │   │   ├── __init__.py
│   │   │   └── scraper_schema.py    # Pydantic models
│   │   │
│   │   ├── utils/                   # Helper utilities
│   │   │   ├── __init__.py
│   │   │   ├── html_parser.py       # Section-aware parsing
│   │   │   ├── text_cleaner.py      # Cleans extracted text
│   │   │   └── logger.py            # Centralized logging
│   │   │
│   │   └── exceptions/              # Custom exceptions
│   │       ├── __init__.py
│   │       └── scraper_exceptions.py
│   │
│   └── tests/                       # Backend tests
│       ├── __init__.py
│       └── test_scraper.py
│
├── frontend/
│   ├── templates/
│   │   └── index.html               # Main UI template
│   │
│   ├── static/
│   │   ├── css/
│   │   │   └── styles.css
│   │   ├── js/
│   │   │   └── app.js               # API calls & rendering
│   │   └── assets/
│   │
│   └── README.md                    # Frontend documentation
│
├── docs/
│   ├── ARCHITECTURE.md              # System design & flow
│   ├── API_REFERENCE.md             # Endpoint documentation
│   └── DESIGN_NOTES.md              # Design decisions
│
├── scripts/
│   ├── run.sh                       # Linux / macOS runner
│   └── run.ps1                      # Windows runner
│
├── capabilities.json                # Feature capability definitions
├── requirements.txt                 # Python dependencies
├── .gitignore
├── README.md                        # Main project README
└── LICENSE                          # (Optional but recommended)

```

---

## 🛠️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/vetchayateesh/Universal_Website_Scraper.git
cd Universal_Website_Scraper
```

###  2. Create and activate a virtual environment

```bash
python -m venv venv
source venv/bin/activate       # macOS / Linux
.\venv\Scripts\activate        # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Install Playwright

```bash
playwright install
```
---
## Running the Project

### Start the API server
```bash
uvicorn backend.main:app --reload
```
---
## Access the UI
```bash
http://localhost:8000
```
---
## 🔍 Usage Overview

Enter the URL of the website you want to scrape.

- The scraper intelligently determines whether to use static HTML scraping or Playwright for dynamic content.

- Extracted content is structured into logical sections like Hero, Navigation, Footer, FAQ, etc.

- View the JSON result in the built-in viewer and download if needed.
---
## 📦 Output Format
The scraper returns a JSON object with:

- Website metadata

- Structured text grouped by logical sections

- Option to export the data for further analysis or integration

## Example snippet:
```bash
{
  "url": "https://example.com",
  "sections": {
    "header": {...},
    "main": {...},
    "footer": {...}
  },
  "timestamp": "2025-12-XXTXX:XX:XXZ"
}

```
---
## 🤝 Contributing

Contributions are welcome! You can:

- Report bugs

- Suggest features

- Submit pull requests

Please follow the repository’s issue templates and coding standards.
---

## 📄 License

This project does not yet specify a license. Consider adding a license file (e.g., MIT, Apache-2.0) to clarify usage rights.
---

## 📌 About

Universal Website Scraper was developed as an MVP full-stack assignment with a focus on robustness, clarity, and real-world usability. It’s ideal for anyone looking to build powerful scraping tools backed by modern Python frameworks.
---
