# Learn CSS FCC

CSS( Cascading Style Sheets ) is a style sheet language used for describing the presentation of a document written in a markup language like HTML. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

## Sequence of being read

from top to bottom, last read will be applied.

## Validation of CSS

W3C CSS Validator

## CSS Selectors

Three levels of selectors:

1. Element Selector(Lowest Priority)

```css
body {
  background-color: lightblue;
}

p {
  color: purple;
  font-size: 64px;
}
```

2. Class Selector(Middle Priority)

```css
.gray {
  background-color: gray;
}
```

3. ID Selector (Highest Priority)

````css
id is unique,
class is not ```css #id {
  color: red;
}
````

## Group CSS Selectors

- comma in between

```css
h1,
h2 {
  color: blue;
}
```

- nested selectors

```css
ul li {
  color: red;
}
```

## Universal Selector

```css
* {
  color: green;
}
```

## `font` related is inherited

```css
body {
  font-family: Arial, sans-serif;
}
```

## `border` related is not inherited

```css
body {
  border: 1px solid black;
}
```

## button, input, select, textarea are not inherited

```css
button,
input,
select,
textarea {
  font: inherit;
  /* then it will be inherited font-family: inherit; */

  font-size: inherit;
  line-height: inherit;
}
```

## `main` element

## `!important` flag

**It overrides all other styles. Only use it when necessary. It is considered bad practice to use !important.**

```css
p {
  color: red !important;
}
```

## Specificity Calculator

[Specificity Calculator](https://specificity.keegan.st/)

Specificity Calculator was built by Keegan Street. The specificity calculator JavaScript module is available on GitHub or via npm install specificity.

Specificity Calculator is built for CSS Selectors Level 4.

Care has been taken to ensure results are accurate. If you find a defect, please report it.

## Set background color

### Three ways to define color:

1. alphabetical
2. hexadecimal (red, green, blue)
   > A hexadecimal color code starts with a hash symbol (#).  
   > It is followed by six characters, which are hexadecimal digits. These digits can be numbers from 0 to 9 and letters from A to F.  
   > The first two digits represent the red component of the color, the next two represent the green component, and the last two represent the blue component.  
   > Each pair of digits can range from 00 (0 in decimal, indicating no presence of that color) to FF (255 in decimal, indicating the maximum presence of that color).
   - shorthand:
     > If your CSS rule uses the same number for adjacent hex values, you can condense them to one.  
     > For example, #FF0000 can be shortened to #F00.  
     > This shortened form gives one digit for red, one digit for green, and one digit for blue.  
     > This reduces the total number of hex digits from six to three.
3. rgb
4. rgba (alpha is transparency)
5. hsl(hue, saturation, lightness)

```css
body {
  background-color: white;
}
```

- shorthand

```css
body {
  background: rgb(0, 0, 0);
}
```

### Set font color

```css
body {
  color: #ffffff;
}
```

### rgba transparency

```css
body {
  color: rgba(0, 0, 0, 0.5); /* 0.5 is transparency, range 0 to 1 */
}
```

### hsl

### hsl(hue, saturation, lightness)

- hue: 0 to 360
- saturation: 0% is gray, 100% is full color
- lightness: 0% is black, 100% is white

## Tools for color

- [collors](https://coolors.co)
  - It can evaluate the contrast between two colors.
  - Pick a color and it will generate a color palette for you.
- [webaim](https://webaim.org)

## CSS Units

### Data Types

<table class="table table-bordered">
      <tbody><tr>
      <th style="text-align: left; width: 10%">Data type</th>
      <th style="text-align: left">Description</th>
      <th style="text-align: left">Example</th>
      </tr>
      <tr>
      <td>&lt;integer&gt;</td>
      <td>Represents a whole number</td>
      <td>55, -55, etc.</td>
      </tr>
      <tr>
      <td>&lt;number&gt;</td>
      <td>Represents a decimal number. It may or may not have a decimal point.</td>
      <td>1.5, 234, -1.5, etc.</td>
      </tr>
      <tr>
      <td>&lt;dimension&gt;</td>
      <td>Represents a &lt;number&gt; with a unit attached to it. Also includes value types such as &lt;length&gt;, &lt;angle&gt;, &lt;time&gt; and &lt;resolution&gt;</td>
      <td>5px, 30deg, 2s, 2.5dpi</td>
      </tr>
      <tr>
      <td>&lt;percentage&gt;</td>
      <td>Represents a fraction of other value, that is, it is always relative to other value.</td>
      <td>80%, 25%, etc.</td>
      </tr>
   </tbody>
</table>

**Be ware of relative and absolute units.**

### CSS Absolute Length Units

<table class="table table-bordered">
      <tbody><tr>
      <th style="text-align: left; width: 10%">Data type</th>
      <th style="text-align: left">Description</th>
      <th style="text-align: left">Example</th>
      </tr>
      <tr>
      <td>&lt;integer&gt;</td>
      <td>Represents a whole number</td>
      <td>55, -55, etc.</td>
      </tr>
      <tr>
      <td>&lt;number&gt;</td>
      <td>Represents a decimal number. It may or may not have a decimal point.</td>
      <td>1.5, 234, -1.5, etc.</td>
      </tr>
      <tr>
      <td>&lt;dimension&gt;</td>
      <td>Represents a &lt;number&gt; with a unit attached to it. Also includes value types such as &lt;length&gt;, &lt;angle&gt;, &lt;time&gt; and &lt;resolution&gt;</td>
      <td>5px, 30deg, 2s, 2.5dpi</td>
      </tr>
      <tr>
      <td>&lt;percentage&gt;</td>
      <td>Represents a fraction of other value, that is, it is always relative to other value.</td>
      <td>80%, 25%, etc.</td>
      </tr>
   </tbody>
</table>

### CSS Relative Length Units

<table class="table table-bordered">
  <tbody>
    <tr>
      <th style="text-align: left; width: 10%">Unit</th>
      <th style="text-align: left">Description</th>
      <th style="text-align: left">Example</th>
    </tr>
    <tr>
      <td>em</td>
      <td>Relative to the font-size of the element.</td>
      <td>font-size: 4em;</td>
    </tr>
    <tr>
      <td>ex</td>
      <td>Relative to the x-height of the current font.</td>
      <td>font-size: 4ex;</td>
    </tr>
    <tr>
      <td>ch</td>
      <td>Relative to width of the "0".</td>
      <td>font-size: 4ch;</td>
    </tr>
    <tr>
      <td>rem</td>
      <td>Relative to font-size of the root element.</td>
      <td>font-size: 2rem;</td>
    </tr>
    <tr>
      <td>lh</td>
      <td>It is relative to the line height of the element.</td>
      <td>font-size: 4lh;</td>
    </tr>
    <tr>
      <td>rlh</td>
      <td>It is relative to the line height of the root element.</td>
      <td>font-size: 4rlh;</td>
    </tr>
    <tr>
      <td>vh</td>
      <td>
        It is relative to the height of the viewport. 1vh = 1% or 1/100 of the
        height of the viewport.
      </td>
      <td>font-size: 4vh;</td>
    </tr>
    <tr>
      <td>vw</td>
      <td>
        It is relative to the width of the viewport. 1vw = 1% or 1/100 of the
        width of viewport.
      </td>
      <td>width: 4vw;</td>
    </tr>
    <tr>
      <td>vmin</td>
      <td>
        It is relative to the smaller dimension of the viewport. 1vmin = 1% or
        1/100 of the viewport's smaller dimension.
      </td>
      <td>width: 4vmin;</td>
    </tr>
    <tr>
      <td>vmax</td>
      <td>
        It is relative to the larger dimension of the viewport. 1vmax = 1% or
        1/100 of the viewport's larger dimension.
      </td>
      <td>width: 4vmax;</td>
    </tr>
    <tr>
      <td>vb</td>
      <td>
        It is relative to the size of the initial containing block in the
        direction of the root element's block axis. 1vb = 1% of containing
        block's size (block axis).
      </td>
      <td>font-size: 4vb;</td>
    </tr>
    <tr>
      <td>vi</td>
      <td>
        It is relative to the size of the initial containing block in the
        direction of the root element's inline axis. 1vb = 1% of containing
        block's size (inline axis).
      </td>
      <td>font-size: 4vi;</td>
    </tr>
    <tr>
      <td>svw, svh</td>
      <td>
        It is relative to the width and height of the smaller viewport. 1svw =
        1% or 1/100 of the smaller viewport's width and 1svh = 1% or 1/100 of
        the smaller viewport's height.
      </td>
      <td>width: 40svw; height: 40svh;</td>
    </tr>
    <tr>
      <td>lvw, lvh</td>
      <td>
        It is relative to the width and height of the larger viewport. 1lvw = 1%
        or 1/100 of the larger viewport's width and 1lvh = 1% or 1/100 of the
        larger viewport's height.
      </td>
      <td>width: 40lvw; height: 40lvh;</td>
    </tr>
    <tr>
      <td>dvw, dvh</td>
      <td>
        It is relative to the width and height of the dynamic viewport. 1dvw =
        1% or 1/100 of the dynamic viewport's width and 1dvh = 1% or 1/100 of
        the dynamic viewport's height.
      </td>
      <td>width: 40dvw; height: 40dvh;</td>
    </tr>
  </tbody>
</table>

#### Some common use cases

- `px` is absolute unit.
- `rem` is relative to the root element.
- `%` is relative to the parent element.
- `em` is relative to the parent element.
- `ch` is relative to the width of the "0".
- `vw` is relative to the width of the viewport.
  > It's better to use `%` than `vw` if you don't want the horizontal scroll bar show up.

```css
h1 {
  width: 100vw;
}
```

- `vh` is relative to the height of the viewport.

##### `em` vs `rem`

```css
h1 {
  font-size: 3rem;
  padding: 0.5em;
}
```

In this case, font-size has influence on padding and margin.

## CSS Box Model

From inner to outer:

1. content
2. padding
3. border
4. margin

### `box-sizing`

```css
* {
  box-sizing: border-box;
}
```

- `content-box` is default
  > `width` and `height` only apply to content
- no influence on `margin` and `border`
  > because `margin` and `border` are outside of a box.
- `border-box`
  > `width` and `height` apply to content, padding and border

### margin shorthand

```css
.container {
  margin: 0 auto; /* top and bottom is 0, left and right is auto */
  margin: 0 auto 0 auto; /* top, right, bottom, left */
  margin: 1.5rem 2rem 0; /* top, right and left, bottom */
  padding: 0 20px;
  border: 1px solid black;
}
```

### compute tab in browser

use it to check the box model

### border-top-style

so many border related properties

### outline

outline is outside of border.

- outline-style
- outline-color
- outline-width
- outline-offset
  > this value can be negative
- outline

### CSS Rounded Borders

```css
.radius {
  border: 100px solid red;
  border-radius: 50px;
}
```

When `border-radius` is half of `border`, it will be a circle.
