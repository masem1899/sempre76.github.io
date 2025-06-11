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

🔎 **pyseoa** is a fast, extensible Python library for analyzing SEO health across one or more URLs, with CLI support too. It performs audits for metadata, accessibility, structered data, performance scores, and more.



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



## 🧪 Python usage
{% highlight python %}
from pyseoa import SEOAnalyzer

# Create SEOAnalyzer instance
analyzer = SEOAnalyzer('https://example.com')

# Start full analyzing
# NOTE: informations via google pageSpeed insights API are only collected 
# if you provide a API key in the constructor.
analyzer.run_full_analysis()

# Export the analysis to a json file
analyzer.export_to_json('report.json')
{% endhighlight %}



## 🧪 CLI Usage

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



## 📤 Output

- JSON report(s) in a folder (default: `seo_reports/`)
- Combined CSV summary (default: `seo_summary.csv`)
- Logs for any failed URLs in `seo_errors.log`
