# Content Updates

Two primary goals of this website's architecture are for content updates to occur **automatically** and **quickly**. With no manual intervention except a `git push`, updates to articles should be viewable within a minute or two. The strategies described below elaborate on the approaches taken to achieve these goals.

## Pull from GitHub at Runtime

The initial architecture for this website expected the service to pull the contents of [`journal`](https://github.com/andrew-selvia/journal) from GitHub at runtime. Conceptually, this would have ensured that the service always showed the latest contents. During development, it became clear that all of the raw Markdown files must be present when they are transformed to HTML. If single files were transformed upon request, the navigation tree Laika generates would be inaccurate.

In order for the *pull* model to work given this constraint, an implementation was created which retrieved the entire `journal` repo from GitHub dynamically upon request of any file (with the eventual goal of adding a caching layer). Early failed attempts at this implementation used GitHub APIs such as the [*Get Repository Content*](https://docs.github.com/en/rest/reference/repos#get-repository-content) & [*Get a Tree*](https://developer.github.com/v3/git/trees/#get-a-tree) APIs; unfortunately, those simply allow walking the hierarchy, not retrieving the files' *contents*. Eventually, the discovery of the [*Download a Repository Archive*](https://developer.github.com/v3/repos/contents/#download-a-repository-archive) API enabled retrieving the contents themselves in .zip format. The next challenge then became extracting the .zip contents within the Scala service; eventually, [this code helped to unzip the contents](https://www.baeldung.com/java-compress-and-uncompress#unzip). Unfortunately, in the end, it eventually became clear that the archives retrieved from that API took on the order of 15 minutes to become available following a commit to the repo's main branch. This delay was deemed unacceptable and the *pull* model was abandoned.

## Push to Google Cloud Storage via a GitHub Action

After the *pull* model proved unfeasible, the *push* model was explored. Eventually, a successful 3-part architecture solidified:

1. A commit to the main branch of `journal` triggers a GitHub Action which transforms the raw Markdown files to HTML.
2. The GitHub Action uploads all the files to Google Cloud Storage (GCS) as described in [*Upload Files to Google Cloud Storage*](/md/software/developer/github/actions/upload-files-to-google-cloud-storage.md).
3. The service dynamically fetches the requested file from GCS.
