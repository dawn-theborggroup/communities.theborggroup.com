# communities.theborggroup.com: rules for any Claude chat

This repository IS the live communities site. Netlify (project **borg-communities**) publishes it
automatically from the `main` branch. Every file here is the original, complete site.

## How to change the site
1. Make a branch, edit the files, open a pull request into `main`.
2. Dawn reviews and merges. Merging publishes the site. Never merge for her.
3. Never push straight to `main`.

## Never do these
- **Never upload or deploy this site by hand** (Netlify Drop, drag-and-drop, `netlify deploy`,
  the Netlify deploy tool, or any zip/folder upload). A partial upload on Nov 17, 2026 replaced the
  whole site with 26 pages and took down the market reports, the homepage "Sell With Us" widget,
  the redirects and the sitemap. The only way to publish is a merged pull request.
- **Never copy a page from the live website** (curl, "save page", browser fetch) and commit it.
  Netlify strips `data-netlify="true"` from forms when it serves pages, and injects a
  `netlify-rum-container` script. A page copied from the live site has broken lead forms.
  Always edit the file in this repository.
- Never delete `_redirects`, `_headers`, `sitemap.xml`, `market-reports/` or `widgets/`.

## Things to keep in mind
- Lead forms use Netlify Forms: every `<form name="...">` must keep `data-netlify="true"`
  (and `netlify-honeypot="bot-field"` where a bot-field input exists).
- `widgets/sell-with-us/` is embedded on the www.theborggroup.com homepage by iframe.
- Market report numbers load live from https://borg-market-data.netlify.app/ (a separate site,
  refreshed by a daily scheduled task); this repository holds only the report pages.
- Every page carries the same canonical footer and the Google Analytics tag G-Q8YTWVXK2J.
- New community pages go under their area folder (for example `estero/<community>/index.html`)
  and get an entry in `sitemap.xml`.
- American English spelling; natural, conversational question-and-answer language.
