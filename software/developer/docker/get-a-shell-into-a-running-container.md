# Get a Shell into a Running Container

While troubleshooting, you may find yourself wanting to get a shell into a running container so you can execute commands directly within it. When faced with this challenge, you can execute the following command to get a `bash` shell into it:

```shell script
CONTAINER=
docker exec -it $CONTAINER bash
```
