# Change Link Colors in Dark Mode

When adding support for Dark Mode to a web page, the browser's default link colors remain static. They are ill-suited for most dark interfaces, though. To change link colors in either system appearance, you can leverage CSS variables:

```css
:root {
    --link-color: #001ae4;
    --link-visited-color: #4e2286;
}

@media(prefers-color-scheme: dark) {
    :root {
        --link-color: #0A84FF;
        --link-visited-color: #5E5CE6;
    }
}

a {
    color: var(--link-color);
}

a:visited {
    color: var(--link-visited-color);
}
```

## References

* [*CSS `:visited` Selector*](https://www.w3schools.com/cssref/sel_visited.asp)
* [Human Interface Guidelines: Color](https://developer.apple.com/design/human-interface-guidelines/macos/visual-design/color)