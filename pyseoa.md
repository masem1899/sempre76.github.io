---
layout: default
title: 'pyseoa - Python SEO library and CLI tool'
show_side_panel: true
side_panel:
  project_section:
    - title: 'PyPi project'
      badge: 'PyPi-project-green'
      link: 'https://pypi.org/project/pyseoa/'
    - title: 'GitHub repository'
      badge: 'GitHub-repository-green'
      link: 'https://github.com/sempre76/pyseoa'
  support_section:
    - title: 'Python'
      badge: 'python-3.7+-blue'
      link:  'https://www.python.org/'
    - title: 'Python'
      badge: 'python-3.11-blue'
      link: 'https://www.python.org/'
  powered_section:
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

🔎 **pyseo** is a fast, extensible Python library for analyzing SEO health across one or more URLs, with CLI support too. It performs audits for metadata, accessibility, structered data, performance scores, and more.



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
# NOTE: informations via google pageSpeed insights API are only collected if you provide a API key in the constructor.
analyzer.run_full_analysis()

# Export the analysis to a json file
analyzer.export_to_json('report.json')
{% end highlight %}



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
