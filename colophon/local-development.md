# Local Development

To serve this website locally for easy development, you may want to use the NGINX Docker image with an attached volume as described in [this article](https://www.docker.com/blog/how-to-use-the-official-nginx-docker-image/). For example:

```shell
docker run -it --rm -d -p 8080:80 --name web -v ~/site-content:/usr/share/nginx/html nginx
```

That's easier than running a file server on you Mac's hardware directly as demonstrated [here](https://tech-cookbook.com/2020/11/14/setting-up-your-local-web-server-on-macos-big-sur-11-0-1-2020-mamp-macos-apache-mysql-php/#Start_the_Apache_Server).

If you need to open the Safari Web Inspector for an iOS device, you can follow the process described [here](https://apple.stackexchange.com/a/339240).
