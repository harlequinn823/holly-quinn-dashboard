# Holly Quinn · Technical.ly article archive

A portable, static dashboard for searching Holly Quinn’s Technical.ly reporting. Built with HTML, CSS and JavaScript; no npm install, API keys, database or build step required.

## Run locally

From this folder, run:

```sh
python -m http.server 8000
```

Open http://localhost:8000. Use a web server rather than opening index.html directly, because the app fetches articles.json.

## Put it on GitHub

Create a repository and upload the contents of this folder, including articles.json and logo.png. Keep index.html at the repository root. You can also use GitHub Desktop to add this folder and publish it as a repository.

The repository can remain private for source storage. Publishing the website is a separate step; the private access controls on the ChatGPT-hosted version are not part of this code. This static export has no authentication.

## Files

- index.html: dashboard structure and controls
- style.css: responsive styles and Technical.ly navy/green palette
- app.js: full-text search, date and topic filters, pagination, CSV export
- articles.json: 2,863 article records, captured October 28, 2026
- logo.png: supplied Technical.ly logo

## Features

Search headlines, summaries and article text for people, companies or phrases. Put a phrase in quotation marks for exact phrase matching. Filter by market, suggested topic, company, year, month, exact date or inclusive custom date range. Rolling date shortcuts cover one, six or twelve months. Sort by newest, oldest or title and export filtered metadata as CSV. Search filters are preserved in the URL.

## Data and limitations

Source: https://technical.ly/wp-json/wp/v2/posts?author=264
Author archive: https://technical.ly/author/hollyquinn/

The included data is a snapshot spanning 2015–2026, not a live feed. No background update service is included. Update articles.json to add or correct records; the app reads it on page load. Keep the updated field in YYYY-MM-DD format accurate.

Markets originate in publisher city tags. Company names are formatted from publisher tag slugs and may need capitalization corrections. Topics are suggested using headline, tag, series and disclosure rules; they are not a manually verified taxonomy. Person and company matches include incidental mentions. Underwriting detection may be incomplete. Open each original article to verify its context.

Record format:

```json
{
  "updated": "2026-10-28",
  "expected": 2863,
  "articles": [
    {
      "id": 123,
      "date": "2026-10-01",
      "title": "Example title (schema illustration only)",
      "url": "https://technical.ly/",
      "excerpt": "Short summary",
      "text": "Plain article text for searching",
      "markets": ["Delaware"],
      "companies": ["Example Company"],
      "topics": ["Education"],
      "tags": ["education"]
    }
  ]
}
```

The example above illustrates the schema only and is not an included article.

## Content and branding

Article text and Technical.ly branding retain their existing ownership and rights. This export does not grant an open-source license to those assets. The JSON includes article text, so making the repository or a static deployment public also exposes that dataset.

The package contains no ChatGPT hosting identifiers, Git history, credentials or service-specific deployment configuration.
