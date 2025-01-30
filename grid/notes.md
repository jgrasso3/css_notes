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

start at 1 and span 2 tracks. If we don't define a start, it will determine where it should start itself

```
.container .item {
  grid-column-start: 1;
  grid-column-end: span 2; // spans over 2 tracks
}
```

#### Grid Area

`grid-column/row: 1 / span 2` is shhorthand for grid-column/row-start&end

`grid-area row start / col start / row end / col end` is the shorthand for grid-column&row

#### Grid Lines

You can line the grid lines in the container to help with positioning instead of working with the numbers.

Don't have to provide 2 names

```
.container {
  display: grid;
  grid-template-column: [col1-start] 1fr [col1-end col2-start] 1fr [col2-end col3-start] 1fr [col3-end]
}

.container .item {
  grid-column-start: col1-start;
  grid-column-end: col1-end;
}
```

#### Grid Template Area

shorthand to setup grid in a visually friendly way. `Show Area Names` in layout dev tools will visualize it for you

Assign grid items a section using `grid-area: <label>`

**Note:** defined areas have to be a box. square or rectangle

`a` and `b` are 2 x 1 and `c` is 1 x 2
```
.container {
  grid-template-area:
    "a a c"
    "b b c";
}

.container .item {
  grid-area: a;
}
```

#### Putting it Together

Define a layout and then assign areas

Layout: navbar top, sidebar right, main area middle

Can leave empty areas by using a `.`

```
.container {
  grid-template-column: 1fr 150px;
  grid-template-row: 100px 1fr 100px;
  grid-template-area:
    "navbar navbar"
    "main sidebar"
    ". footer";
}

.container .nav {
  grid-area: navbar;
}
```

## Dynamic Grids

### Grid Auto Flow

Specify how the grid adds new items. Defaults to row.

The `dense` keyword will change the grid algo to attempt to fill smaller holes earlier if they exist

```
.container {
  grid-auto-flow: column dense;
}
```

### Auto rows and cols

The 1st 8 items will explicitly fit in the grid as defined. `auto-rows` will automatically give new items a height of 200px to all items that would overflow normally

```
.container {
  grid-template: reapeat(2. 200px) / repeat(4, 200px);
  grid-auto-flow: row;
  grid-auto-rows: 200px;
}
```

### Responsive Grids

`auto-fill` and `auto-fit` can be used as the 1st arg in `repeat()` and will let the browser decide how many columns will fit

`repeat(auto-fill, minmax(300px, 1fr)` will add as many cols as it can with a min width of 300px, and expand them to fill some empty space
* leave space for an extra column if no more content

`repeat(auto-fit, minmax(300px, 1fr)` will add as many cols as it can with a min width of 300px, and expand them to fit all empty space
* collapse empty space and allow items to take that space

```
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr);
}
```

