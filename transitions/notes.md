# Transitions

Smooths movement of elements. Animatie from 1 state to another.

## Basic

transition: <property> <duration> <timing-func> <delay>;

units
  * s: seconds
  * ms: milleseconds

most transitions will be under a second

defining the transition in the element itself, it will apply **anytime** that property changes

```css
/* takes 1 second for backgropund to change colors, regardless of what initiates it */
a.btn {
  transition: background-color 1s;
}

/* transition will only apply during the hover action, but won't when you stop hovering */
a.btn:hover {
  background-color: orange;
  transition: background-color 1s;
}
```

## Multiple Transitions

comma separate in the `transition` key. can specify **all** but not recommended

```css
a.btn:hover {
  background-color: orange;
  color: white;
  transition: background-color 1s, color 1s;
}
```

## Timing Funcs

specifies the rate at which the time happens at

* examples
  * linear
  * ease-in
  * ease-out

[cool example blog](https://www.kirupa.com/html5/timing_functions.htm)

[bunch of examples](https://easings.net/)

## Transition Delays

postpone the start of the transition

```css
/* transition takes 2 seconds to start */
a {
  transision: background-color 1s, ease-in 2s
}
```

## Performance

* some properties are performance heavy when it comes to animating
  * margin
  * width

* most performant properties that only affect composite calcs
  * opacity
  * transform

* browser rendering
  * JS
  * ---
  * style calc
  * layout: calc how much space an element takes up
  * ---
  * painting: browser fills in the pixles
  * composite: takes the painted layers and combines them into 1 to draw on screen

## Transform

* The most performant property to animate. Lets you rotate, scale, ske, or translate an elem. 
  * leaves the og space behind where the elem was

* docs
  * [transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
  * [translate](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate)
  * [rotate](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate)
  * [scale](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale)

`transform: <func>(values)`

### Translate

```css
.box {
  /* shifts the box along the x-axsis by 50% of its width */
  tranform: translateX(50%);
}
```

### Roate

cool for spinning rotate loading animations

default rotation point is the center

defaults to z, but can rotate on:
  * x for towards
  * y like a globe

```css
h1 {
  /* rotates 90deg from the middle */
  tranform: rotate(90deg);
}
```

### Scale

* takes in a unitless number.
  * 1 means to keep at og scale

* defaults to X and Y but can also each both individually

```css
.box {
  /* makes the box twice as wide and 4 times tall */
  tranform: scale(2, 4);
}
```

## Origin

define the origin of a transformation

takes in keywords, pixles, or both

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)

```css
.box {
  /* roate the box 45deg from the top left point */
  tranform: rotate(45deg);
  transform-origin: top left;
}
```
