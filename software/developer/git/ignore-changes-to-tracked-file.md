# Ignore Changes to Tracked File

Have you ever wanted a repo to store a file in a given default state but ignore local changes to it? For instance, if you need to store secrets in a configuration file but don't want to commit them to the repo or have them appear as changed every time you go to make a commit, you may have stumbled upon this situation. If you add the file to `.gitignore` after it has been tracked, changes will still appear for staging. An in-depth analysis of the options is available [on StackOverflow](https://stackoverflow.com/questions/653454/how-do-you-make-git-ignore-files-without-using-gitignore). The solution that fits the criteria best in this case involves updating the index:

```shell
git update-index --skip-worktree $FILE
```

Then to reverse it:

```shell
git update-index --no-skip-worktree $FILE
```
