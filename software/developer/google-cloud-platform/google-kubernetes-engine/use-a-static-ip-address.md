# Use a Static IP Address

Assuming you have an app running on Google Kubernetes Engine (GKE) and a domain name through which you'd like to expose it, you are likely wondering how to connect the two. Luckily, [*Configuring Domain Names with Static IP Addresses*](https://cloud.google.com/kubernetes-engine/docs/tutorials/configuring-domain-name-static-ip) provides a thorough guide to the steps involved including how to:

* [Expose your application](https://cloud.google.com/kubernetes-engine/docs/tutorials/configuring-domain-name-static-ip#step_2_expose_your_application) as either a [Service](https://cloud.google.com/kubernetes-engine/docs/tutorials/configuring-domain-name-static-ip#step_2a_using_a_service) or an [Ingress](https://cloud.google.com/kubernetes-engine/docs/tutorials/configuring-domain-name-static-ip#step_2b_using_an_ingress)
* [Configure your domain name records](https://cloud.google.com/kubernetes-engine/docs/tutorials/configuring-domain-name-static-ip#step_4_configure_your_domain_name_records)
* [Test if your app is reachable via its domain name](https://cloud.google.com/kubernetes-engine/docs/tutorials/configuring-domain-name-static-ip#step_5_visit_your_domain_name)
