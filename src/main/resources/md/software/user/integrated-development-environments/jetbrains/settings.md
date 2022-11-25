# Settings

The first thing you should consider is how to manage your settings. If you'll be using multiple JetBrains products, working across various computers, or want to share your settings with your entire team, you should reference the JetBrains documentation on how to [*Share IDE Settings*](https://www.jetbrains.com/help/webstorm/sharing-your-ide-settings.html). In particular, the use of a [settings repository](https://www.jetbrains.com/help/webstorm/sharing-your-ide-settings.html#settings-repository) can dramatically simplify synchronizing settings across various JetBrains products.

Here are some settings you may consider using within your JetBrains IDEs:

* Close button position: This setting defines where the close button is rendered on a tab. It defaults to the right side. This stands in opposition to the tab close button location throughout the rest of macOS. In order to change it to be more consistent, follow these steps:

    1. Choose **App > Preferences...** (⌘,)
    2. Disclose **Editor > General**
    3. Choose **Editor Tabs**
    4. Set **Appearance > Close button position** to **Left**
    5. Choose **OK**

* Use custom font: Perhaps you already knew that you can choose a custom font for use within JetBrains IDEs. However, did you know that you can set it to be the standard system font on macOS? This is convenient because as Apple changes the font used throughout the system, the IDE can always look like it fits in. Follow these steps to enable it:

    1. Choose **App > Preferences...** (⌘,)
    2. Disclose **Appearance & Behavior > Appearance**
    3. Set **Use custom font** to **.SF NS Text**
    4. Choose **OK**

* Editor font: Similarly to the general IDE font, you can set the editor font to the system monospace font like this:

    1. Choose **App > Preferences...** (⌘,)
    2. Disclose **Editor > Font**
    3. Set **Font** to **.SF NS Mono**
    4. Choose **OK**

* Markdown preview CSS rules: You can slightly modify [the Markdown preview style](https://www.jetbrains.com/help/webstorm/markdown.html#css), though you should not get too greedy. Ultimately, you don't control the Markdown-to-HTML conversion, so you're not able to do things like add support for custom code syntax highlighting. The preview **cannot** fully emulate your production style. However, you can at least change a few basic things like the fonts.

    1. Choose **App > Preferences...** (⌘,)
    2. Disclose **Languages & Frameworks > Markdown**
    3. Set **Custom CSS > Add CSS rules** to:
        
       ```css
        body {
            font-family: SF Hello;
        }
        
        code {
            font-family: SF Mono;
        }
        ```
       
    4. Choose **OK**

* Copyright: If you need to add copyright declarations to all your source files, you can use the Copyright plugin as described in [its documentation](https://www.jetbrains.com/help/webstorm/copyright.html).
* Dictionary: If you want to configure a dictionary so the editor doesn't show spelling errors, refer to the documentation on how to set up a [dictionary](https://www.jetbrains.com/help/idea/spellchecking.html#configure-the-dictionaries-to-use).
