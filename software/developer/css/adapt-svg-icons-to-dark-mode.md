# Adapt SVG Icons to Dark Mode

When Dark Mode is enabled, you must adapt icons so they look correct. You can leverage `currentColor` as described in [*Making Single Color SVG Icons Work in Dark Mode*](https://hiddedevries.nl/en/blog/2018-12-24-making-single-color-svg-icons-work-in-dark-mode).

You may also find this code helpful:

```css
:root {
    --navbar-button-fill: #292929;
    --navbar-button-hover-fill: #000000;
}

@media(prefers-color-scheme: dark) {
    :root {
        --navbar-button-fill: #D6D6D6;
        --navbar-button-hover-fill: #FFFFFF;
    }
}

.button {
    fill: var(--navbar-button-fill);
}

.button:hover {
    fill: var(--navbar-button-hover-fill);
}
```

It uses variables to control the fill color of SVG buttons in normal & hover states.