# Bootstrap

Imagine you get a brand new Mac running a clean installation of macOS. It's beautiful, but its default settings frustrate you. How do you get it set up just like the old one without using Migration Assistant? If you've ever joined a company and been allocated a Mac, you've undoubtedly faced this dilemma. Luckily, you're not alone. In order to bootstrap you macOS environment with your accustomed System Preferences, applications, credentials, and other artifacts, you should leverage the wisdom of other engineers who have gone before you.

## System Preferences

For instance, the de facto resource for configuring System Preferences is [this script](https://github.com/mathiasbynens/dotfiles/blob/main/.macos). For more details on how to look up and modify these preferences, refer to [*Change macOS User Preferences via Command-line*](https://pawelgrzybek.com/change-macos-user-preferences-via-command-line).

## App Store Apps

The best way to automate the installation of applications from the Mac App Store is [mas](https://github.com/mas-cli/mas).
