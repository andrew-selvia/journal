# Configure Memory Resources

To configure the amount of memory available to a container, you can specify an amount in the Pod definition. For more details, refer to [the official documentation](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/#meaning-of-memory). [This StackOverflow answer](https://stackoverflow.com/a/50805048/6073927) also helps clarify the difference between the two notations for defining a memory amount:

> 1. 5 G = 5000000 KB (5000 MB)
> 2. 5 Gi = 5368709.12 KB (5368.70 MB)