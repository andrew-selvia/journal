# Host a Website

Deciding how to host a website is multifaceted. Factors which may influence the decision include: price, development time, deployment convenience, and control. Thankfully, there exist many hosting platforms today which offer solutions targeting those factors in different proportions. This article attempts to encapsulate the tradeoffs associated with some of them.

## Host a Website on a Publishing Platforms

The simplest way to get started is almost certainly an established publishing platform. Each offers slight variations on the same idea: provide a platform for people to create websites without having to write or manage software or infrastructure. One category of publishing platforms is social networks like [Facebook](https://facebook.com), [Twitter](https://twitter.com), [Instagram](https://instagram.com), [Reddit](https://reddit.com), [Tumblr](https://tumblr.com), and [Medium](https://medium.com). These sites make it easy to produce & share content for free. The price is applied to ownership. All content on these platforms is owned by the platform which handles advertising and distribution. Custom domains, design, and server-side logic are impossible. Convenience has a cost; weigh it heavily before proceeding.

If you want more control over the design of your website without adopting ownership of the data model or distribution infrastructure, solutions like [Squarespace](https://squarespace.com), [WordPress](https://wordpress.com), and [Ghost(Pro)](https://ghost.org/pricing) may fit your needs. All offer some form of a what-you-see-is-what-you-get (WYSIWYG) theme editor which enables limited customization of important design elements like fonts, colors, and images. These platforms charge reasonable prices given the infrastructure burdens they lift off your hands and their rich integration ecosystems.

[*How is Ghost different?*](https://ghost.org/docs/concepts/introduction/#how-is-ghost-different) provides a lucid comparison of Ghost, WordPress, and Medium that highlights the core differences between each platform. Prior to deciding where to publish your content, you should review it thoroughly.

### Ghost

Within the category of publishing platforms, Ghost is unique in that it is fully open source. As a result, you could choose to [self-host](https://ghost.org/docs/concepts/hosting/#self-hosting) your website built upon the Ghost platform. Assuming you have relevant development experience and you're comfortable with their architectural and design decisions, this can be a powerful, *free* alternative. Of course, consider [the tradeoffs](https://ghost.org/docs/concepts/hosting/#ghostpro) associated with that decision first.

To evaluate whether Ghost is the right choice for your website, refer to its documentation:

* [Features](https://ghost.org/docs/concepts/features)
* [Ecosystem](https://ghost.org/docs/concepts/ecosystem)
* [Hosting](https://ghost.org/docs/concepts/hosting)
* [Self-hosted Server Recommendations](https://ghost.org/docs/concepts/server-recommendations)
* [Self-hosted Configuration](https://ghost.org/docs/concepts/config)
* [Theme Marketplace](https://ghost.org/marketplace)

## Host a Website Created by a Static Site Generator

If you want to break free of the most highly-opinionated PaaS providers, there are a few solutions which enable you to have more control while still lifting the burden of cloud infrastructure management. Often, they still rely on a static site generator which makes some assumptions about project structure. Overall, though, these solutions are more portable since you control the content source.

### GitHub Pages

Assuming you can commit to using git for source control and hosting your repository (repo) on [GitHub](https://github.com), [GitHub Pages](https://pages.github.com) offers a remarkably convenient service for free. With built-in support for [Jekyll](https://jekyllrb.com), GitHub Pages makes deploying a static website as simple as pushing your changes to GitHub. Each commit to the master branch results in an automated deployment within a few minutes. To learn more about the basics, refer to [*About GitHub Pages*](https://docs.github.com/en/github/working-with-github-pages/about-github-pages).

The time-to-market of GitHub Pages is hard to beat. The tradeoffs can be restrictive for certain use cases, though. Most importantly, your website must be static; there can be no server-side logic. This limitation isn't always relevant; however, if your site needs to store data or connect with other services, you may find yourself wanting to build that functionality on the server-side.

Obviously, the convenience of GitHub Pages also incurs a loss of control. There are limitations to the number of deployments that can be made within an hour. Scaling out the website, post-processing, and tool selection are all constrained. For instance, Jekyll is the default static site generator for GitHub Pages. If you want to use another static site generator, you can technically [bypass Jekyll](https://github.blog/2009-12-29-bypassing-jekyll-on-github-pages) (perhaps with [Sphinx](https://www.docslikecode.com/articles/github-pages-python-sphinx)), but your repo will then be required to store the output HTML files in the repo directly. There is no way to avoid checking in changes to the output files since GitHub Pages will refer to a directory containing the output files to serve the site.

Of course, Jekyll has its own constraints. Jekyll requires articles to reside within the `_posts` directory and be named in a specific format (i.e. `2020-08-06-my-article.md`). While such rules may be good heuristics for blogs, they aren't as applicable to other publications like [digital gardens](digital-gardening.md).

### Netlify

A common step up from GitHub Pages is [Netlify](https://www.netlify.com). It attempts to [overcome some of the limitations of GitHub Pages](https://www.netlify.com/github-pages-vs-netlify) (i.e. more frequent deployments, support for additional static site generators, 1-click rollbacks, and server-side logic) while still offering the convenience of push-activated deployments. Netlify even partially overcomes the limitations of pure static sites by offering integration with serverless computing services like AWS Lambda.

Netlify achieves a happy medium that will satisfy the needs of most sites that outgrow GitHub Pages, however it is still largely focused on serving the needs of static sites. As long as you are comfortable with that constraint, it is a great choice.

## Host a Website on a Cloud Platform

If you would like to host more just than static content (i.e. services of your own) while still avoiding infrastructure procurement and maintenance, modern cloud platforms are a great solution. Using [Amazon Web Services (AWS)](https://aws.amazon.com), [Google Cloud Platform (GCP)](https://cloud.google.com), [Linode](https://www.linode.com), [Heroku](https://www.heroku.com), or various others, you can host your website on rented infrastructure. These solutions are generally not free and require moderate technical experience, but offer much more freedom at the architectural level.

A full review of these platforms' offerings is out-of-scope for this article, but luckily most offer some high-level guidance:

* [AWS: Web Hosting](https://aws.amazon.com/websites)
* [AWS: Host a Static Website](https://aws.amazon.com/getting-started/projects/host-static-website)
* [AWS: Hosting a Static Website on Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html)
* [GCP: Hosting a Static Website](https://cloud.google.com/storage/docs/hosting-static-website)
* [Linode: Host a Static Site using Linode Object Storage](https://www.linode.com/docs/platform/object-storage/host-static-site-object-storage)
* [Linode: Deploying a Static Site on Linode Kubernetes Engine](https://www.linode.com/docs/kubernetes/how-to-deploy-a-static-site-on-linode-kubernetes-engine)
* [Heroku: Getting Started](https://devcenter.heroku.com/start)
