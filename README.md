# News Scraper API

[![Oxylabs promo code](https://user-images.githubusercontent.com/129506779/250792357-8289e25e-9c36-4dc0-a5e2-2706db797bb5.png)](https://oxylabs.go2cloud.org/aff_c?offer_id=7&aff_id=877&url_id=112)

Oxylabs’ [News Scraper](https://oxylabs.io/products/scraper-api/web/news-scraper?utm_source=github&utm_medium=repositories&utm_campaign=product) is a data gathering solution allowing you to extract real-time information from any news website effortlessly. This brief guide explains how a News Scraper works and provides code examples to understand better how you can use it hassle-free.

### How it works

You can get news results by providing your own URLs to our service. We can return the HTML for any news page you like.

#### Python code example

The example below illustrates how you can get HTML of a [nbcnews.com](https://www.nbcnews.com/world) page.

```python
import requests
from pprint import pprint

# Structure payload.
payload = {
    'source': 'universal',
    'url': 'https://www.nbcnews.com/world'
}

# Get response.
response = requests.request(
    'POST',
    'https://realtime.oxylabs.io/v1/queries',
    auth=('user', 'pass1'),
    json=payload,
)

# Instead of response with job status and results url, this will return the
# JSON response with the result.
pprint(response.json())
```
Find code examples for other programming languages [**here**](https://github.com/oxylabs/news-scraper/tree/main/code%20examples)

#### Output Example
```json
{
  "results": [
    {
      "content": "<!DOCTYPE html><html lang=\"en\"><head><link href=\"https://nodeassets.nbcnews.com/_next/static/css/525 ... </html>",
      "created_at": "2023-12-18 11:37:17",
      "updated_at": "2023-12-18 11:37:24",
      "page": 1,
      "url": "https://www.nbcnews.com/world",
      "job_id": "7142477922073389057",
      "status_code": 200
    }
  ]
}
```
With our News Scraper, you can seamlessly extract public data from any News web page. Gather crucial information such as breaking news, opinion articles, or editorial pieces, to understand the current trends and stay informed. If you have any questions, reach out to our support team via live chat or email us at hello@oxylabs.io.
