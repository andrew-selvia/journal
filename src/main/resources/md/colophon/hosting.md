# Hosting

The priorities and decisions which have led to the current hosting strategy for this website are recorded here.

## Priorities

* Articles must be written in Markdown for ease of writing & reading as plain text while also enabling distribution via the web (after transformation to HTML).
* Articles must be contained within a hierarchy of directories branching from a root directory which is managed by git for source control.
* The repo's organizational structure should not be determined by an external system (i.e. Jekyll enforces strict naming and organization of directories).
* The raw data (articles) should be separated from the manufacturing process (Markdown to HTML) and service which publishes them so that alternate data could easily be fed into the publication pipeline. 
* Commits to the main data branch should trigger automatic processes which manufacture all pages into HTML and publish them for distribution by the service.
* Costs should be minimized, though need not be 0.
* The publication pipeline runtime should be minimized so that new articles are visible in production within just a couple minutes.
* The site must use a custom domain.
* The site must be distributed over https.
* All data & code artifacts must always remain open-source so a global community can leverage, improve, and adapt them over time.

## Decisions

The initial rollout of this website was influenced by the assumption that it would leverage server-side logic in the future. If you refer to the history of this document, you can read about the initial strategy that involved hosting Markdown files on GitHub, transforming them to HTML files, uploading those to Google Cloud Storage, then fetching them dynamically from a service running on Google Kubernetes Engine. The initial price was $5 per month. Unfortunately, the actual cost wound up being $50 per month due to my own ignorance most likely.

In addition to the surprising costs, I also had to face the reality that I don't have time to develop server-side logic for this project. Furthermore, it became clear that the service was doing nothing but forward static files upon request. The sensible decision became obvious: just host static content. While AWS or GCP could perform that task, the new direction lent another opportunity to investigate GitHub Pages.

My previous experiences with GitHub Pages had all left me feeling unfulfilled. I was certainly not interested in jumping back into Jekyll due to its enforced structure and dependence on Ruby. Luckily, the initial round of development on this website had already proven the concept of using Laika to transform Markdown files to HTML files ready for serving. Aided by [this discussion](https://github.community/t/non-jekyll-website/126216), I was able to work out how to use GitHub Pages like a simple file server. In the end, I came to peace with the exchange of control over the website's deployment and hosting for the unbeatable free price.
