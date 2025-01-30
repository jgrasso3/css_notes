# Box Model

content w/i a border, with padding inside, and margins separateing boxes

### Borders
border-width
      -color
      -style
border: width style color

### Controlling Content Dimensions
width: px
height: px

### Instead of Px, you can use %S
width: 50%;

### Padding
padding: 20px; hits all sides with 20px
padding: top right bottm left

### Margins
Spacing outside of the border, between elements

same syntax as padding

### Alt Box Model
set `box-sizing: border-box;` to enable on an element
Setting height and width will set the dimensions for the entire box, including border and padding

### Display Property
Sets whether an element is displayed as block or inline

**block**: breaks onto new line, uses width and height, padding and margin forcefeild, tries to fill whole horizantal space

**inline**: no new line, ignores w & h, no vertical forcefeild

**inline-block**: no new line, uses w & h, whole forcefeild

### Display None
`display: none` removes a whole element from the page

Good for mobile vs desktop nav bars

### Negative margins and margin auto

Margins can be negative

margin: 0 auto; have no vertical margin, but try to center horizantal

### Margin Collapse

2 stacked block level elements, the webpage will use the larger margin rather than combine them

However, horizantal margins DO NOT collapse

### Common Layout Pattern

you can wrap many elements in a div to group together, then can add spacing to the container instead of individually

### Min and Max width

`width: 60%; min-width: 300px` take up 60% of the screen but never get lower than 300px

### Border Radius

Change rounding of corners in a box

`border-radius: 5% | 10px`

### Box Shadows

Adds a shadow around the box to add depth

`border-shadow: x y blur color`

### Overflow

Default of content is to overflow outside the box. Can be controlled by `overflow`

options:
  * visable (default)
  * hidden
  * scroll
