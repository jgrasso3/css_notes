# Backgrounds

* properties:
  * background-image
  * background-repeat
  * background-color
  * background-clip
  * background-position
  * background-size
  * background-attachment

## image

smaller images will repeat itself to fill the space

can have a comma sepparated list of images to stack them

`background-image: url("path");`

## Repeat

make the background repeat or not

* inputs
  * no-repeat
  * repeat-x | y
  * repeat

`background-repeat: no-repeat`

## Size

contain: scale the image as large as possible w/o cropping or stretching

cover: scale image as much as possible while preserviing the ratio to the smallest possible size to fill the container

`background-size: cover`

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size)

## Position

set the initial position of the img relative to the container

input:
  * keywords: top, left, center, bottom, etc
    * can use mutliple keywords
  * values

`background-position: center bottom`

## Clip

Where the background img extends underneeth

typical inputs: border-box, padding-box, content-box

`background-clip: content-box`

# Gradients

## Linear

Transition of 2+ colors on a straigh line

You can stack them by comma sep `linear-gradient()`s

`background-image: linear-gradient(cyan, magenta);`

```css
.box {
  height: 400px;
  width: 400px;
  background-image: linear-gradient(cyan, magenta);
}
```

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient)

## Other

* [radial](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/radial-gradient)
* [conic](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/conic-gradient)
* various repeating

## Shorthand

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/background)

```css
background: url('path') no-repeat center/200%;
```

## Filters

Like adding filters to instagram post

`filters: greyscal() contrast(100%);`

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)
