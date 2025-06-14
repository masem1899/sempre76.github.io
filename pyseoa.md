---
layout: default
title: 'pyseoa - Python SEO library and CLI tool'
show_side_panel: true
side_panel:
  sections:
    - section:
      title: Site
      items:
        - title: 'PyPi project pyseoa'
          badge: 'PyPi-project-green'
          link: 'https://pypi.org/project/pyseoa/'
        - title: 'pyseoa GitHub repository'
          badge: 'GitHub-repository-green'
          link: 'https://github.com/sempre76/pyseoa'
        - title: 'PyPi pyseoa downloads by pepy.tech'
          link: 'https://pepy.tech/projects/pyseoa'
          img: '<img src="https://static.pepy.tech/badge/pyseoa" alt="PyPI Downloads">'
    - section:
      title: "Docker 🐳"
      items:
        - title: Docker pulls
          link: 'https://hub.docker.com/repository/docker/masemcontact/pyseoa/general'
          img: '<img src="https://img.shields.io/docker/pulls/masemcontact/pyseoa?style=flat-square" alt="docker image pulls>'
        - title: Docker image version (latest)
          link: 'https://hub.docker.com/repository/docker/masemcontact/pyseoa/general'
          img: '<img src="https://img.shields.io/docker/v/masemcontact/pyseoa/latest?style=flat-square" alt="docker image version (latest)">'
    - section:
      title: "Support"
      items:
        - title: 'Python'
          badge: 'python-3.7+-blue'
          link:  'https://www.python.org/'
        - title: 'Python'
          badge: 'python-3.11-blue'
          link: 'https://www.python.org/'
    - section:
      title: "Powered by":
      items:
        - title: 'BeautifulSoap4'
          badge: 'BeautifulSoup4-pypi-6d9cbe'
          link: 'https://www.crummy.com/software/BeautifulSoup/'
        - title: 'Requests'
          badge: 'Requests-Homepage-3776ab'
          link: 'https://requests.readthedocs.io/'
        - title: 'tqdm'
          badge: 'tqdm-GitHub-4b8bbe'
          link: 'https://github.com/tqdm/tqdm'

      
---
# pyseoa
[![PyPI](https://img.shields.io/pypi/v/pyseoa)](https://pypi.org/project/pyseoa/)

## 🚀 Python SEO Analyzer — CLI, Library & Web 📦

`pyseoa` is a modern, thread‑ready Python toolkit for deep‑dive SEO audits.  
Use it as a library, CLI tool, or integrate with FastAPI for web apps.

---

## 🔍 Features (v0.2.3)

- ✅ **Single & Batch Analysis**
  - Run SEO checks on one or multiple URLs via crawl or direct URL  
  - Smart internal link crawling and multithreading for performance  

- ⚙️ **Feature Flags**
  Easily enable or disable checks via bitflags:
  - Title, Meta description, H1, Image alts  
  - Canonical, OpenGraph, Twitter meta  
  - Robots.txt, Sitemap, Favicon  
  - Accessibility hints, Structured Data (JSON‑LD), Mobile-friendliness  
  - Keyword density (with custom allow/deny lists)  
  - Hreflang, Meta‑robots, Web Vitals, AMP compliance  

- 📄 **Exporters**
  - JSON, CSV, Markdown  
  - Fancy HTML report with styles  
  - PDF (via FPDF)  
  - Terminal summary  

- 🔄 **Threaded Workflow**
  - Multi-threaded crawling, analysis, and exporting  
  - Optional progress bars via `tqdm`

- 🐍 **CLI Tool & API Support**
  - Run via `pyseo‑analyze` CLI:  
    ```bash
    seo-analyze https://example.com --crawl --export html
    ```  
  - Fully importable — works great with FastAPI, Flask, Streamlit, Dash, etc.

---

## ⚡ Install

```bash
pip install pyseoa
# or, specify version:
pip install pyseoa==0.2.3
```

---

## 🧾 Basic Library Example

```python
from pyseoa import SmartBatchSEOAnalyzer

urls = ["https://example.com", "https://another.com"]
analyzer = SmartBatchSEOAnalyzer(urls, follow_links=True)
analyzer.run_batch_analysis()

# Save outputs
analyzer.exporters.json.export(analyzer.results)
analyzer.exporters.csv.export(analyzer.results)
analyzer.exporters.html.export(analyzer.results, output="report.html")
```

---

## 🏃‍♂️ CLI Usage

Analyze a single site:
```bash
seo-analyze https://example.com
```

Batch or crawled analysis:
```bash
seo-analyze --crawl --export html urls.txt
```

Run `seo-analyze --help` for full options list.

---

## 🧩 Integration with Web Apps

E.g. With FastAPI or Flask in your web project:

```python
from fastapi import FastAPI, Form
from pyseoa import SmartBatchSEOAnalyzer

app = FastAPI()

@app.post("/analyze")
def analyze(url: str = Form(...), crawl: bool = Form(False)):
    analyzer = SmartBatchSEOAnalyzer([url], follow_links=crawl)
    analyzer.run_batch_analysis()
    return analyzer.results
```

---

## 🔧 Command-Line Installer

Install via Git:
```bash
git clone https://github.com/sempre76/pyseoa.git
cd pyseoa
pip install -e .
```

---

## 📦 What's New in v0.2.x

- Dynamic internal link crawling  
- Feature flags overhaul  
- New exporters: Markdown, PDF, Terminal  
- Multi-threaded pipelines with progress bars  
- Web integration: SmartBatchAnalyzer & FastAPI-ready

---

## 👥 Contributing

PRs welcome! Please check:

- **Code**: `pip install .`, run basic analyzers  
- **Tests**: run under example projects or use CLI  
- **Docs**: update examples & feature flags in README

---

## 📜 License & Author

- **MIT License** – see the [LICENSE](LICENSE) file  
- **Maintained by masem** – contact: contact@masem.at

---

## 🔗 Links

- 🔗 **PyPI**: [https://pypi.org/project/pyseoa/](https://pypi.org/project/pyseoa/)  
- 🧪 **GitHub**: [https://github.com/masm1899/pyseoa/](https://github.com/sempre76/pyseoa/)  
- 🌐 **Web UI Demo**: [seo.masem.at](https://seo.masem.at) (Powered by FastAPI)
- 📘 See also FastAPI companion project: [masem-seo-web](https://github.com/sempre76/masem-seo-web)

