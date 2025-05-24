---
title: 
date: 2025-05-24
---

# Simple Usage of SEOAnalyzer in Python
This Example shows, how to use the SEOAnalyzer class. An instance of the class will be created, then the whole analysis were running and the result were exported to json.

## Example Source

{% highlight python %}
from pyseoa import SEOAnalyzer

# Create SEOAnalyzer instance
analyzer = SEOAnalyzer('https://example.com')

# Start full analyzing
# NOTE: informations via google pageSpeed insights API are only collected if you provide a API key in the constructor.
analyzer.run_full_analysis()

# Export the analysis to a json file
analyzer.export_to_json('report.json')
{% endhighlight %}


## Example Output `report.json`

{% highlight json %}
{
  "title": "Example Domain",
  "meta_description": "Missing",
  "h1_tags": [
    "Example Domain"
  ],
  "image_count": 0,
  "missing_alt_tags": [],
  "canonical_url": "Missing",
  "og:title": "Missing",
  "og:description": "Missing",
  "twitter:title": "Missing",
  "twitter:description": "Missing",
  "robots_txt": "Missing",
  "sitemap_xml": "Missing",
  "favicon": "Missing",
  "keyword_density": [
    {
      "word": "domain",
      "count": 4,
      "percent": 16.0
    },
    {
      "word": "example",
      "count": 2,
      "percent": 8.0
    },
    {
      "word": "illustrative",
      "count": 1,
      "percent": 4.0
    },
    {
      "word": "examples",
      "count": 1,
      "percent": 4.0
    },
    {
      "word": "documents",
      "count": 1,
      "percent": 4.0
    },
    {
      "word": "literature",
      "count": 1,
      "percent": 4.0
    },
    {
      "word": "without",
      "count": 1,
      "percent": 4.0
    },
    {
      "word": "prior",
      "count": 1,
      "percent": 4.0
    },
    {
      "word": "coordination",
      "count": 1,
      "percent": 4.0
    },
    {
      "word": "asking",
      "count": 1,
      "percent": 4.0
    }
  ],
  "mobile_friendly": "Likely",
  "internal_links": 0,
  "external_links": 1,
  "nofollow_links": 0,
  "hreflang_tags": 0,
  "meta_robots": "Missing",
  "core_web_vitals": "No google pagespeed insights API key specified.",
  "accessibility_issues": [
    "Missing semantic landmarks (main/nav/header/footer)"
  ],
  "structered_data": "None found",
  "seo_score": 30
}
{% endhighlight %}