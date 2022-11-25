# Use Environment Variables in Integrated Development Environments

Assuming you are using a Mac, you want to run an application in an integrated development environment (IDE) (i.e. Xcode, IntelliJ IDEA, etc.), and it depends on the presence of secrets exposed as environment variables, you have likely faced the dilemma of deciding how to inject the secrets. At first, maybe you just hard-code them in your code. Obviously, that is remarkably risky for any code which is under source control since you might accidentally forget to remove the secrets before committing. Next, you might try storing them in environment variables in your shell; you might even save them in your shell profile (i.e. `.zshrc`, `.bash_profile`, etc.). While those approaches will enable your app to work if it's launched from the terminal, they won't enable your app to run from an IDE normally since IDEs are not launched directly from a shell.

At this point, most people would just resolve to store the environment variables in their IDE. Most modern IDEs do support manually injecting environment variables. However, there is another option. You can use [`launchctl`](https://ss64.com/osx/launchctl.html) to expose an environment variable across the *entire* operating system, including apps. Just restart your IDE afterward to see the changes take effect. For instance:

```shell script
launchctl setenv ENVIRONMENT_VARIABLE VALUE
```

Also, there are apparently [ways to trigger `launchctl` automatically when you log in to your computer](https://stackoverflow.com/a/36161817/6073927). Those are left as an exercise.
