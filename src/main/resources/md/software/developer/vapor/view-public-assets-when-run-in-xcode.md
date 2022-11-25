# View Public Assets When Run in Xcode

If you have assets in the `Public` directory and you [correctly configure the `FileMiddleware`](https://docs.vapor.codes/4.0/folder-structure/#public), Vapor should be able to serve them automatically. However, if you run your app in Xcode, you may be surprised to discover that your assets are not accessible. According to [the documentation](https://docs.vapor.codes/4.0/xcode/#custom-working-directory):

> By default Xcode will run your project from the DerivedData folder. This folder is not the same as your project's root folder (where your Package.swift file is). This means that Vapor will not be able to find files and folders like .env or Public.

To resolve this issue, you must do the following:

1. Open your project in Xcode.
2. Choose **Product > Scheme > Edit Scheme...** (⌘<)
3. Choose the **Run** action
4. Choose the **Options** tab
5. Choose **Use custom working directory**
6. Input the path to your project

Afterward, your app should be able to serve Public assets when run via Xcode.
