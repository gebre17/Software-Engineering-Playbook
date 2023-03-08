# Python Automation

Python is an excellent language for automating boring, repetitive, or complex operating system and web tasks.

## 1. Web Scraping & API Interaction
*   **Requests / HTTPX:** For making HTTP calls to REST APIs.
*   **BeautifulSoup:** Parse HTML and extract page elements.
*   **Playwright / Selenium:** For browser automation, scraping dynamically rendered SPAs, and UI workflows.

```python
import httpx
from bs4 import BeautifulSoup

def scrape_title(url):
    response = httpx.get(url)
    soup = BeautifulSoup(response.text, "html.parser")
    return soup.title.string
```

## 2. File & Directory Orchestration
Using `pathlib` for robust cross-platform path management.

```python
from pathlib import Path

# Create a directory and check existence
log_dir = Path.cwd() / "logs"
log_dir.mkdir(exist_ok=True)

# Write to file
file_path = log_dir / "app.log"
file_path.write_text("Execution started.\n")
```

## 3. Scheduled Tasks
*   **Schedule:** Lightweight local scheduler library.
*   **APScheduler:** Advanced Python Scheduler (supports cron jobs, intervals).
*   **Celery:** Distributed task queue for heavy processing workloads.
