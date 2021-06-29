# Disable Permanent Hover Effects on Touch-screen Devices

If your webpage shows a hover effect on an element, it likely works properly when used with a mouse; however, you may be surprised to see the hover effect become permanent when interacted with via a touch-screen device. To disable hover effects on touch-screen devices exclusively, refer to [this StackOverflow answer](https://stackoverflow.com/questions/17233804/how-to-prevent-sticky-hover-effects-for-buttons-on-touch-devices/54556732#54556732). It is summarized below:

```css
.element {
    color: red;
}
.element:hover {
    color: blue;
}
@media (hover: none) {
    .element {
        color: red;
    }
}
```
