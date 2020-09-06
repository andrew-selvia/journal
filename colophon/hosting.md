# Hosting

When the decision of how to host this site was made, a few high-level priorities guided the process:

* Articles must be written in Markdown for ease of writing & reading as plain text while also enabling distribution via the web (after transformation to HTML).
* Articles must be contained within a hierarchy of directories branching from a root directory which is managed by git for source control.
* The repo's organizational structure should not be determined by an external system (i.e. Jekyll enforces strict naming and organization of directories).
* Manufactured HTML files should not be preserved in git, only the raw articles.
* The raw data (articles) should be separated from the manufacturing process (Markdown to HTML) and service which publishes them so that alternate data could easily be fed into the publication pipeline. 
* Commits to the main data branch should trigger automatic processes which manufacture all pages into HTML and publish them for distribution by the service.
* Costs should be minimized, though need not be 0.
* The publication pipeline runtime should be minimized so that new articles are visible in production within just a couple minutes.
* The site must use a custom domain.
* The site must be distributed over https.
* All data & code artifacts must always remain open-source so a global community can leverage, improve, and adapt them over time.

Hosting providers (such as those described in [*Host a Website*](/todo/host-a-website.md)) were evaluated based upon these criteria. In the end, the decision came down to either AWS or GCP since they enable hosting a service as opposed to just a static website. GCP was the final choice due to its more appealing user interface, competitive pricing, and superior Kubernetes experience.

## Pricing

The initial plan to keep costs at 0 by using GitHub Pages quickly came into conflict with other priorities, specifically to have server-side logic. Next, Heroku was considered due to its convenience, but was ruled out since it abstracts the deployment infrastructure (particularly, Kubernetes) too far away. Next, the free tiers of [Amazon Web Services (AWS)](https://aws.amazon.com/free) & [Google Cloud Platform (GCP)](https://cloud.google.com/free) were evaluated. Unfortunately, AWS only offers 12 months of free EC2 instances. While GCP offers a f1-micro instance through GCE for free each month, early testing proved that the memory constraints on that node were too small to effectively run the service.

With no apparent free solution that met the requirements for the website, cost requirements were relaxed slightly. AWS & GCP both offer competitive prices, but neither differed drastically from each other; AWS: $5.40/month (for [1 *spot* t3.small instance](https://aws.amazon.com/ec2/spot/pricing)) & GCP: $3.54/month (for [1 *preemptible* g1-small machine](https://cloud.google.com/compute/vm-instance-pricing#sharedcore)). Caution: the previous comparison isn't perfect! The two machine types aren't identical; t3.small instances have more memory & CPU than g1-small machines. Nonetheless, the differences are irrelevant for the purposes of this website. With price floors being relatively consistent, the choice of hosting provider was simplified to other factors, specifically cloud console design and Kubernetes experience. This led to GCP being chosen.

For more information or to re-evaluate the pricing in the future, refer to the following links:

* [AWS: EC2 Instance Types](https://aws.amazon.com/ec2/instance-types)
* [AWS: Spot Pricing](https://aws.amazon.com/ec2/spot/pricing)
* [GCP: Machine Types](https://cloud.google.com/compute/docs/machine-types)
* [GCP: VM Instance Pricing](https://cloud.google.com/compute/vm-instance-pricing)