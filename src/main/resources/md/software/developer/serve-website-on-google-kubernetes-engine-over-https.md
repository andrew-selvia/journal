# Serve Website on Google Kubernetes Engine over HTTPS

In order to serve a website over HTTPS, it must be equipped with SSL certificates. While integrating SSL certificates into an app deployed on Google Kubernetes Engine (GKE) does not stray fundamentally from that rule, there are a few intricacies to observe. The following references should help you achieve your goal.

## Use Self-managed Certificates

If you plan to use self-managed certificates, you may want to begin by reading these articles:

* [*Let's Encrypt: Getting Started*](https://letsencrypt.org/getting-started)
* [*Google Cloud – SSL Certificates the Easy Way*](https://www.jhanley.com/google-cloud-ssl-certificates-the-easy-way)

## Use Google-managed Certificates

If you plan to use Google-managed certificates, you should begin by reading the official documentation:

* [*SSL Certificates Overview*](https://cloud.google.com/load-balancing/docs/ssl-certificates): This describes the basics of SSL certificates, including some details about the differences between [*Self-managed and Google-managed SSL Certificates*](https://cloud.google.com/load-balancing/docs/ssl-certificates#certificate-types).
* [*Using Google-managed SSL Certificates*](https://cloud.google.com/load-balancing/docs/ssl-certificates/google-managed-certs): If you decide to use Google-managed certificates, this guide provides a thorough description of the steps required.
* [*Google-managed SSL Certificate Domain Status*](https://cloud.google.com/load-balancing/docs/ssl-certificates/troubleshooting#domain-status): If the certificates aren't working as expected or you just want to test them, the command described [here](https://cloud.google.com/load-balancing/docs/ssl-certificates/troubleshooting#domain-status) should help you troubleshoot the cause of the issue.
