# Flexbox Basics

* a layout method for laying items in rows and columns
* allows us to distribute space dynamically across elems of unknown size

## Terms

* flex container: some parent elem where display si set to flex
* flex items elems inside a flex container
* main axis: 
* cross axis: 

## Flex Direction

controls the main axis of out content. Great for defininf row based or column based content

`flex-direction: row;`

values:
  * row
  * row-reverse
  * column
  * column-reverse

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction)

## Flex Wrap

default behavior is not not wrap any content and to instead shrink content to fit

`flex-wrap: wrap` will enable wrapping

values:
  * no-wrap
  * wrap
  * wrap-reverse
    * flips the cross axis and wraps above instead

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap)

## Justify Content

Set how to distribute the content on the main axis

`justify-content: flex-start`

values:
  * flex-start: put all white space to the end
    * end: white space at the start
      * looks like row-reverse, but order is still left to right
  * center: evenly distribute white space on both ends
  * space-between: content touches both ends, distributes white space evenly between content
    * cool for nav bars
  * space-around: distributes white space evenly between content
    * all elems have the same space between

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)

## Align Items

Used to align elements across the **cross-axis**

`align-items: flex-start;`

values:
  * stretch: stretch elems across the cross-axis to take up all the space
  * flex-start: align elements at the beginning of the corss-axis
    * end
  * center

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)

## Align Content

Controls the space between wrapping

**note:** Won't do anything w/o wrapping, ie multiple rows or columns

`align-content: ;`

values:
  * flex-start: place all content at the top of cross
    * end
  * center: no space between wraps, all on the outside
  * space-between: take any leftover space and put between wraps
    * opposite of center
  * space-around

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content)

## Align Self

Same concept as `align-items` but applied to an individual **flex item**

OG space is maintained for moved items

`align-self: flex-end`

values: see `aligh-items`

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self)

# More Flex

Flex shothand prop sets how an item grows or shrinks to fit the space available in the container

`flex: <flex-grow> <flex-shrink> <flex-basis>`

## Flex Grow

Dictates how much of the available space inside the flex con the item should take up

**note:** still respect max widths and heights

`flex-grow: 1;` vs `flex-grow: 2` takes twice as much empty space **1**

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow)

## Flex Shrink

Sets the flex shrink factor of an item. 

If the size of all flex items is larger than the flex container, items shrink to fit according to flex-shrink

`flex-shrink: 3` shrinks 3 times faster than `flex-shrink: 1`

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink)

## Flex Basis

Sets the initial main size of a flex item.

Sets the size of the content-box unless otherwise set with box-sizing (width/height)

`flex-basis: 1000px;`

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis)

## Flex Shorthand

`flex: <flex-grow> <flex-shrink> <flex-basis>`

flex: <take up whitespace rate> <shrink to fit rate> <start at this size>

keywords:
  * **initial**:
    * sized according to width and height. Shrinks to min size to fit container, but does not absorb free space
    * `flex: 0 1 auto`
  * **auto**:
    * aized according to width and height. Shrinks to min size to fit container, and absorbs free space
    * `flex 1 1 auto`
  * **none**: 
    * sizes according to width and height. **fully inflexible**, does not shrink or grow w/ relation to container
    * `flex: 0 0 auto`

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)

## Order Flex

Defines the order of when to place an item in the container. 

Defaults to the order defined in the markup

Cool for screen readers. Need date to visually come first but Title should come first for readers

`order: -1` make an item come first

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/order)

## Flexbox Patterns

margin-<whatever> is your friend

### Navbar

can use `margin: auto` to justify content to a separate side

```css
```

### Nesting Containers

can nest multiple containers to organize data

```css
```

### Centering Content

### Card Layout


