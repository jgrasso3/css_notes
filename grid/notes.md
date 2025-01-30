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

### Other columns and row styles


