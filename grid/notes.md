# Grid

## Basics

Flex controls 1 direction, row or column, while grid controls both.

`display: grid` to enable. `inline-grid` makes the containing div act like an inline element similar to `inline-block`

`fr` i.e fraction of the grid. They will eat up any leftover, like `flex-grow`

A block grid w/ 150px ad column on right, 20rem on right, and mid column that takes up the middle by 3 eql rows
```
.container {
  display: grid;
  grid-template-columns: 150px 1fr 20rem;
  grid-template-rows: 1fr 1fr 1fr;
}
```

`grid-template: 1fr 1fr 1fr / 150px 1fr 20rem` is eql to the example above. it goes rows / cols

## Other columns and row styles

### MinMax

`grid-template-columns: minmax(100px, 1fr)` will set a min col width of 100px and max of 1 fr. Can be chained for multiple cols

```
.container {
  display: grid;
  grid-template-columns: minmax(100px, 1fr) 1fr;
  grid-template-rows: minmax(100px, auto); // auto will make it fit content
}
```

### Repeat

```
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(4, minmax(100px, auto));
}
```

### Fit Content

`fit-content()` tells grid track to be as wide/tall as its content, but w/ a max. Like inverse of `minmax(100px, auto)`; min val is `auto`

```
.container {
  display: grid;
  grid-template-columns: fit-content(300px) 1fr 1fr;
}
```

### Grid Gaps

Control spacing between grid items on col/row. Does not add space on the outside of items.

* column-gap
* row-gap
* grid-gap // acts like padding and margin

```
.container {
  display: grid;
  grid-template 1fr 1fr / 1fr 1fr 1fr
  grid-gap: 20px 10px;
}
```

## Grid Item Options

Grid line indecies start at 1!

### Position Grid Items

* gid-column/row-start/end:

```
.container {
  display: grid;
  grid-template 1fr 1fr / 1fr 1fr 1fr
}

.container .item {
  grid-column-start: 1;
  grid-column-end: 3; // spans over 2 tracks
  grid-row-start: 2;
  grid-column-end: 3; // 1 track starting at 2
}
```

#### Span

start at 1 and span 2 tracks

```
.container .item {
  grid-column-start: 1;
  grid-column-end: span 2; // spans over 2 tracks
}
```
