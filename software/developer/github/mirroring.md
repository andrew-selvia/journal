# Mirroring

If you need to mirror a repo, you can reference [the examples GitHub lists](https://docs.github.com/en/github/getting-started-with-github/finding-ways-to-contribute-to-open-source-on-github#open-source-projects-with-mirrors-on-github). In general, you'll need to:

1. Configure a post-receive hook on the source repo
2. Have a CI build server or some other service listen for the hook notification
3. Mirror the changes to the destination repo

## References

* <https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/duplicating-a-repository#mirroring-a-repository-that-contains-git-large-file-storage-objects>
* <https://packagecloud.io/github/git-lfs/>
