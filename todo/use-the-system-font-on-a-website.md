# Use the System Font on a Website

Choosing an appropriate font for a website is no easy feat. Both technical and artistic factors are likely to impact the decision. Rather than reinvent the wheel entirely, you may be compelled to simply leverage the default font of the operating system. Luckily, this is possible in modern browsers like Safari.

To use the system font in your website, follow the instructions within the *More CSS Additions* section within [*New WebKit Features in Safari 13.1*](https://webkit.org/blog/10247/new-webkit-features-in-safari-13-1):

> New font keywords are available for using platform-specific fonts including `ui-serif`, `ui-sans-serif`, `ui-monospace`, and `ui-rounded`. 

For instance, this website uses `ui-sans-serif` & `ui-monospace` which render as San Francisco & SF Mono on Safari.

## References

* [*Using the System Font in Web Content*](https://webkit.org/blog/3709/using-the-system-font-in-web-content): Outdated
* [*System Font Stack*](https://css-tricks.com/snippets/css/system-font-stack): Lists the system font on various versions of different popular operating systems.
* [*"system-ui" generic font family*](https://www.chromestatus.com/feature/5640395337760768): Chrome documentation describing how Blink uses "BlinkMacSystemFont" instead