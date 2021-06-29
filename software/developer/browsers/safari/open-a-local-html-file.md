# Open a Local HTML File

If you attempt to open a HTML file that contains emoji directly (i.e. as a file, not via a service), you may be surprised to find that the emoji do not render correctly. In this case, you should declare the following tag within the HTML's `head`:

```html
<meta charset="utf-8">
```
