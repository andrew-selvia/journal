# Favicons

[Favicons](https://www.w3docs.com/snippets/html/how-to-add-an-image-in-the-title-bar.html) are icons provided by webpages for display within browser tabs. They enable quick visual identification.

## Generate Assets

Unfortunately, there is [no universal standard for favicon sizing or routing](https://stackoverflow.com/questions/48956465/favicon-standard-2020-svg-ico-png-and-dimensions). Luckily, [RealFaviconGenerator](https://realfavicongenerator.net) automates the entire process and explains the rationale behind all the assets it produces. Once your actual icon is designed (as a 260x260 PNG or SVG file), simply upload it and follow the steps to create a favicon for all the most common use cases including:

* A desktop browser tab favicon
* A mobile browser tab favicon
* An iOS web app icon

## Verification

The best way to verify your webpage's favicon looks right is to view it on all the platforms you care about. While verifying your favicon on Safari, you may need to [clear the cache](https://www.groovypost.com/howto/clear-the-safari-cache-on-your-iphone/).

## Apple Platform Considerations

Safari supports favicons as documented in [*Creating Pinned Tab Icons*](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/pinnedTabs/pinnedTabs.html#//apple_ref/doc/uid/TP40002051-CH18-SW1). Furthermore, iOS has rich, built-in support for web apps. To leverage this functionality, refer to [*Configuring Web Applications*](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html).

Additionally, you may find the following links generally informative:

* [Apple Human Interface Guidelines: App Icon](https://developer.apple.com/design/human-interface-guidelines/ios/icons-and-images/app-icon/)
* [*Apple-specific Meta Tag Keys*](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html#//apple_ref/doc/uid/TP40008193-SW3)

## Dark Mode Variant

While the web has gained some support for dark mode interfaces, favicons remain slightly out of reach at the time of this writing. Specifically, Safari has only partial support as clarified by [caniuse.com](https://caniuse.com/#feat=link-icon-svg):

> Safari 9+ has support for "pinned tab" SVG icons, but this requires an unofficial `rel="mask-icon"` to be set and only works for all-black icons on Pinned Tabs.

The following articles corroborate this fact:

* [*Are you using SVG favicons yet? A guide for modern browsers.
*](https://medium.com/swlh/are-you-using-svg-favicons-yet-a-guide-for-modern-browsers-836a6aace3df)

    > This method won’t work with the mask-icon since the colour is in the attribute but Safari adds a white background if there isn’t enough contrast.
* [*Dark Mode Favicons*](https://css-tricks.com/dark-mode-favicons/)

    > You specify the color, so there is no opportunity there for a dark mode situation.
* [*Light and dark themed SVG favicon using the CSS prefers-color-scheme media feature*](https://catalin.red/svg-favicon-light-dark-theme/)
* [StackOverflow: Detect if the browser is using dark mode and use a different favicon](https://stackoverflow.com/questions/55170708/detect-if-the-browser-is-using-dark-mode-and-use-a-different-favicon)

For the time being, you may want to consider applying a shade of gray to the mask-icon used by Safari so that it appears reasonably in either Light or Dark Mode, especially since some users may switch throughout the day and the mask-icon is not refreshed when the mode switches. For instance, apple.com uses `#888888`.