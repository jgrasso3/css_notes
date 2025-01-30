Adding style
  <p style='color: blue">
  <style>h1: {color: red}</style>
  <link rel="stylesheet" href="style.css">

color
  color: name || rgba(x,x,x, 0.0->1.0) || #aabbcc
  opacity: 0-100%

Inheritance
  Some features support inheritance, like color. Can be overridden

Styles
  font-family: most-prefered, 'arial', sans-serif, least-prefered, (default if none available); (inherited)
  font-size: 60px;
  font-weight: normal(400), bold(700) || 100-900
  font-style: normal, italic, oblique

Text Alignment
  text-align: center
    aligns based on its element

Spacing
  letter-spacing: 3px
  word-spacing: 5px
  line-height: normal | 5px, 2(multiplier)
    multiplier scales with font size

Custom Fonts
  import into html or css from google fonts
  need to specify every weight and style

Text Shadow
  text-shadow: multiple formats
               x y blur color
               12 -5 2 #ff0
  text-shadow: shadow1, shadow2, etc

Text Transform
  text-transform: uppercase;
  text-decoration-(line, color, etc): underline dotted;
  text-decoration: cyan wavy line-through;

ID Selector
  <span id='actor'>
  #actor { color: blue; }

Class Selector
  <p class='stuff'>
  .stuff { color: red; }

Styling Lists
  list-style-type: disc || "*" || none;
  list-style-position: inside or outside
  list-style-image: url("path");

Styling Links and Hover
  a:visited { color: orange; }
  a:hover { 
    color: red;
    text-decoration: underline;
    cursor: pointer;
  }

Font
  shorthand to set various font properties in 1 line
  h1 {
    font-family: sans-serif;
    font-size: 50px;
    font-weight: 100;

    font: 100 50px sans-serif;
  }

Universal Selector
  * { color: red; }

Attribute Selector
  input[type='email'] { color: green; }
  a[href^="#"] { color: gold; }
    ^=: starts
    $=: ends
    *=: contains

Grouping Selectors
  h1, h2 { color: red; }
  p, .actors { color: yeah; }

Combinators
  Decendant: all nested decendants from the parent
    div h2 { color: red; } No comma between h2 and div
    #cast span { color: blue; }
      only make spans under the cast id blue
  
  Child: only immediate child decendants of parent
    ul > li { border: 1px; }

Compund Selector
  div.special.stuff { color: red; }
    only divs with both classes of special and stuff