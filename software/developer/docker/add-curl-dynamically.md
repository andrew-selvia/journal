# Add curl Dynamically

While troubleshooting a service running in a Docker container, you may find yourself wanting to get a shell into the container so you can run `curl` natively, thereby avoiding any potential networking misconfigurations. However, many images used in production are trimmed such that they lack programs like `curl`. In this situation, recall that you can likely dynamically install programs if you can get a shell. For instance, if your container is based on Ubuntu, you could install `curl` like this:

```shell script
apt-get update && apt-get install -y curl
```