# Combinators

## Siblings

example: `Siblings`

### Adjacent

The `+` combinators selects elements that are directly after the 1st element

```css
/* only paragraphs that come directly after H1s will be selected */
h1 + p {

}
```

### Sibling combinator

The `~` combo selects siblings. Siblings are elements that share the same parent

```css
/* 
  only <p> that have an H1 parent are selected 
  there can be other elements between the p and h1
*/
h1 ~ p {

}
```

## Pseudo Classes

allow us to style states of elements

[examples](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes):
  * hover (user actiion)
  * disabled (forms)
  * visited (location aka links)
  * nth-of-type (tree)
  * not() (logic)

```css
button:hover {}

/* select inputs that have been disabled */
input:disabled {}

a:visited {}

/* select every other element starting at the 1st element. Think zebra tables */
li:nth-of-type(2n + 1) {}

/* select anything that is in the body and not h1-3 */
body :not(h1,h2,h3) {}
```

### Repeating selecting

(2) vs (2n) is select the 2nd element vs selecting every other element

## Pseudo Elements

specify part of a selected element, such as the 1st line of a paragraph.

certain elements have rules to them

[example](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

```css
/* select the 1st paragraph subling's 1st letter */
p:first-of-type::first-letter {}

input::placeholder {}
```

# Specificity

When multiple rules w/ different selectors apply to the same element, which one applies

## Basics

1) inline style
2) ID selectors
3) class | attr | pseudo-class
4) type | pseudo-element

```css
/* class font size and id color will apply */
.class {
  color: blue;
  font-size: 20px
}

#id {
  color: red
}
```

**Inline styles:** The most specific and will always win. Generally want to avoid

## Calculating Specificty Values

**The formula:** num (ID) + num (class | attr | pseudo-class) + num (type | pseudo-element). Poker rules

`h1 + dic + span` vs `class` -> 0 0 3 < 0 1 0

`.special` vs `p:nth-of-type(2)` -> 0 1 0 < 0 1 1

# Cascade

Formula in browser that decides which rule wins whenever theere is a conflict

1) importance
2) origin
3) Specificity
4) Position

[Great example blog post](https://2019.wattenberger.com/blog/css-cascade)

## Importance

We can make a rule as important w/ `!important` flag to put it at the top of the cascade. Try to avoid

```css
h1 {
  color: purple !important;
}
```

## Origin

1) Website
  * what the dev defines
2) User
  * rare
3) Browser
  * default style in the browser

## Position

Order the rules were defined in

**rule**: whichever comes last, wins
