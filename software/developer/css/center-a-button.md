# Center a Button

In order to center a button within a `div`, you can use the following CSS (as discovered on [w3schools.com](https://www.w3schools.com/howto/howto_css_center_button.asp)):

```css
.button {
  margin: 0;
  position: absolute;
  top: 50%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}
```