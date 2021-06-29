# Use `jsonpath` to Format `kubectl` Output

If you need to integrate `kubectl` output into a script, you should be aware of its [`jsonpath` support](https://kubernetes.io/docs/reference/kubectl/jsonpath/) which allows you to format the output precisely as you need it.

If you need to access a key which contains a ".", you should refer to [this GitHub issue comment](https://github.com/kubernetes/kubernetes/issues/23386#issuecomment-305348170). This need commonly arises while attempting to use `kubectl get secrets`. In that case, try something like this:

```shell
kubectl get secrets my-secret -o "jsonpath={.my-object['key-prefix\.key-suffix']}"
```
