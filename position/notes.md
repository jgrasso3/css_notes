# Position

`position` specifies where in the doc an element will go. Can be fine-tuned w/ keywords and `z-index`


* values
  * static
  * relative
  * absolute
  * fixed
  * sticky

## Static

* The default value
* element fits in the normal flow of the doc
* keywords and z-index have no effect

## Realative

* element fits in the normal flow of the doc
* keywords can scoot the element from the default spot
  * inputs push the element
* even if the element is offset, its original space in the doc is maintained
  * you can push the elem to a completely different position, but the space it originally occupied won;t be taken over by neighbors

## Zi_index

* Specifies the elevation of an element relative to other elements
  * aka specifies the order elements stack
* The higher z-index will be on top
* only applies to elements that are not static

[docs](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index)

## Absolute

* elem is removed from the normal doc flow
  * now relative to the nearest parent elem w/ an explicit **position** property
* if no parent has a position prop other than `static`, becomes relative to root container
  * can be any parent it's a descendent of
* no space is left where it used to be!
* can be scooted

## Fixed

* elem is removed from normal flow. positioned relative to root container
* og space is removed
* scootable
* stays in place as you scroll
