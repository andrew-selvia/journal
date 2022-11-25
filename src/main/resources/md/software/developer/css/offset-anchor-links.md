# Offset Anchor Links

[Anchor links](https://www.w3docs.com/snippets/html/how-to-create-an-anchor-link-to-jump-to-a-specific-part-of-a-page.html) allow users of a webpage to jump to specific sections within. This convenience is often exposed through a table of contents.

Unfortunately, if your webpage has a navigation bar, anchor links may appear underneath it by default. To offset anchor links to account for the height of the navigation bar, you may find [the discussion in the comments of this blog post](https://pixelflips.com/blog/anchor-links-with-a-fixed-header) beneficial. Specifically, you should take note of this comment:

```css
:target:before {
content: "";
display: block;
height: 30px;
margin: -30px 0 0;
}
```

## References

* [*Fixed Headers, On-page Links, and Overlapping Content, Oh My!*](https://css-tricks.com/fixed-headers-on-page-links-and-overlapping-content-oh-my/)
* [Can I Use: scroll-padding-top](https://caniuse.com/#feat=mdn-css_properties_scroll-padding-top)
* [StackOverflow: offsetting an html anchor to adjust for fixed header](https://stackoverflow.com/questions/10732690/offsetting-an-html-anchor-to-adjust-for-fixed-header)
