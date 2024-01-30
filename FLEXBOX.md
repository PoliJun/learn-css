# Flexbox

[ **A Complete Guide to Flexbox** ](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

## `flex-flow`

First is direction, second is wrap

```css
.container {
  max-width: 800px;
  min-height: 400px;
  margin-inline: auto;
  border: 1px solid #000;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  flex-flow: row wrap;
  align-content: space-evenly;
}
```

Eventually, you can use these three properties setting any elements.

```css
.box {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

## `flex` shorthand

The first value is `flex-grow` the second value is `flex-shrink` the third value is `flex-basis`

```css
.container {
  display: flex;
  flex: 1 1 250px;
}
```

## `order` property

This will reverse this element

```css
.box:nth-child(2) {
  `order: -1`;
}
```

## Practice

[**Flexbox Froggy**](https://flexboxfroggy.com/)
