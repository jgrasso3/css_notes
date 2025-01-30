# Basics

2 Kinds:
* Relative: specify a length relative to some other value
  * em
  * rem 
  * vh
  * vw
  * %
  * and more
* Absolute
  * px: css px is different from phisical px
  * pt
  * cm
  * in
  * mm

[CSS Lengths Exxplained](https://hacks.mozilla.org/2013/09/css-length-explained/)

## Percentages

A relative value based on property. Could be parent or itself. Look at documentation for guidance

Great for width and height

* `width: 50%`: half width of parent
* `line-height: 50%`: half the font-size of the element itself

## REMs

ROOT EMs: relative to the root html element's font-size. Will scale with user settings, like an old person making text bigger

Root font-size is 20px, 1 rem is always 20px, 2 rem is 40px, etc

## EMs

* Relation to font size:
  * 1em = font-size of parent
  * 2em is twice the parent font-size

* Other properties:
  * 1 em = relative to the computed font-size of the element itself

```css
.container {
  font-size: 30px;
}

h1 {
  font-size: 4em;
  margin: 0;
  margin-left: 2em; /* 2 * (h1.font-size * container.font-size) = 2 * (4 * 30) = 240px */
}
```

## VH and VW

1vw is 1% of the width of the viewport. Same goes for vh

Viewport is the actual size page. A smaller browser window is a smaller viewport

Good for larger layout concerns

* `width: 100%` is 100% of the **parent's** width while `width: 100vw` is 100% of the **viewport's** width
  * if the parent is the **body**, these widths would be the same

## When to use

* PX: avoid for font-sizes. Good for small details like borders and shadows
  * don't scale and unresponsive

* rem/em: go to choice for font-sizes and often padding and margin
  * rem is easier to keep things size relative to each other
  * will scale up and down

* %: useful for defining layouts and widths

* vh/vw: used for larger layout concerns
  * cool for overlays

## Floats

[floats](https://developer.mozilla.org/en-US/docs/Web/CSS/float):
* tells an element to position itself in the left or right side of its container.
* It gets removed from the normal document flow
  * allows text and inline elements to wrap around

![alt text](<Screenshot from 2024-07-31 10-36-40.png>)


