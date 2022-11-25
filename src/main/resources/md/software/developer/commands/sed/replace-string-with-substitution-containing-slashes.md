# Replace String with Substitution Containing Slashes

You may have used `sed` to replace a string before. Normally, you can use it like this:

```shell script
echo "hello world" | sed s/hello/hi/
```

to produce:

```
hi world
```

However, if you attempt to substitute a string which contains slashes as described above:

```shell script
echo $HOME # /Users/username
echo "My home directory is at ~." | sed s/~/$HOME/
```

you will find that `sed` fails with an error similar to this:

```
sed: 1: "s/~//Users/username/": bad flag in substitute command: 'U'
```

As described in [this StackOverflow answer](https://stackoverflow.com/a/16790886/6073927), the cause of this issue is that you have instructed `sed` to use "/" as a delimiter. Luckily, `sed` can easily be configured to use a different delimiter to avoid this problem. For example:

```shell script
echo "My home directory is at ~." | sed s@~@$HOME@
```

Now, the program should work and produce output similar to:

```
My home directory is at /Users/username.
```
