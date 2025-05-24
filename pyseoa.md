---
layout: default
title: pyseoa - Python SEO library and CLI tool
show_side_panel: true
---
# pyseoa

🔎 **pyseo** is a fast, extensible Python library for analyzing SEO health across one or more URLs, with CLI support too. It performs audits for metadata, accessibility, structered data, performance scores, and more.

---

## 🚀 Features

- Analyze single or batch URLs
- Title, meta description, headers, alt tags
- Canonical links, Open Graph, Twitter tags
- Robots.txt, sitemap.xml, favicon check
- Accessibility (A11Y) hints
- Structured Data (JSON-LD)
- Lighthouse score via PageSpeedAPI (optional)
- Mobile-friendly detection
- Keyword density analysis
- Export results to JSON, CSV, or HTML
- Parallel processing with progress bar
- API and CLI ready

---

## 📦 Installation

{% highlight bash %}
pip install pyseoa
{% endhighlight %}

Or form source:
{% highlight bash %}
git clone https://github.com/sempre76/pyseoa.git
cd pyseoa
pip install -e
{% endhighlight %}

---

## 🧪 Usage

### Analyze a single URL
{% highlight bash %}
seo-analyze https://example.com
{% endhighlight %}

### Analyze multiple files from a file

{% highlight bash %}
seo-analyze -f urls.txt
{% endhighlight %}

### Full CLI Options

{% highlight bash %}
seo-analyze -h
{% endhighlight %}

---

## 📤 Output

- JSON report(s) in a folder (default: `seo_reports/`)
- Combined CSV summary (default: `seo_summary.csv`)
- Logs for any failed URLs in `seo_errors.log`

## 🔗 Links

- [PyPi](https://pypi.org/project/pyseoa/0.1.0/)
- [GitHub Repository](https://github.com/sempre76/pyseoa)

[![PyPI version](https://img.shields.io/pypi/v/pyseoa.svg)](https://pypi.org/project/pyseoa/)
[![Python versions](https://img.shields.io/pypi/pyversions/pyseoa.svg)](https://pypi.org/project/pyseoa/)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Downloads](https://static.pepy.tech/badge/pyseoa)](https://pepy.tech/projects/pyseoa)

## 🔌 Powered by

[![Python 3](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![BeautifulSoup4](https://img.shields.io/badge/BeautifulSoup4-pypi-6d9cbe.svg)](https://pypi.org/project/beautifulsoup4/)
[![Requests](https://img.shields.io/badge/Requests-GitHub-3776ab.svg)](https://github.com/psf/requests)
[![tqdm](https://img.shields.io/badge/tqdm-GitHub-4b8bbe.svg)](https://github.com/tqdm/tqdm)

