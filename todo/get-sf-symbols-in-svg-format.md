# Get SF Symbols in SVG Format

Apple's [SF Symbols](https://developer.apple.com/design/human-interface-guidelines/sf-symbols/overview) library provides developers with well-designed iconography for use alongside text within their apps. If you would like to use one of the symbols outside of an app on Apple's platform (for instance, on a website), you will need to export it to a more open format. Thankfully, Dave DeLong has created [`sfsymbols`](https://github.com/davedelong/sfsymbols) for this exact purpose.

The sidebar icon in the top-left of this website was generated with the following `sfsymbols` command: 

```shell script
sfsymbols --output ~/Downloads/symbols --symbol-name sidebar.left --font-weight regular --font-size 28
```