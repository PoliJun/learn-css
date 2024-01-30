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

## form elements are not inherited

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

[box-sizing](https://www.tutorialspoint.com/css/css3_box_sizing.htm)

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

## `text`

```css
p {
  text-decoration: line-through;
  text-indent: 10px;
  line-height: 1.5; /* 1.5 times of font-size, 1.2 is default */
  letter-spacing: 2px; /* space between letters */
  font-weight: 400; /* 400 is default */
  font-style: italic; /* normal is default */
  font-family: Arial, sans-serif; /* sans-serif is default */
}
```

- `font-family` can have multiple choices, if the first one is not available, it will use the second one.

## external font: google font

[google fonts](https://fonts.google.com/)

### `@import` in CSS

At top of CSS file

```css
@import url("https://fonts.googleapis.com/css?family=Lobster");
```

## `a` tag

```css
a {
  color: #0000ff;
  text-decoration: none; /* underline is default, set it to none would omit the underline of the text link */
  cursor: not-allowed; /* default is pointer */
  color: blue; /* default is blue */
}
```

## pseudo class

### Syntax

```css
selector:pseudo-class {
  property: value;
}
```

### Anchor Pseudo-classes

```css
/* unvisited link */
a:link {
  color: #ff0000;
}

/* visited link */
a:visited {
  color: #00ff00;
}

/* mouse over link */
a:hover,
a:focus {
  /* focus is for keyboard navigation (tab) */
  color: #ff00ff;
}

/* selected link */
a:active {
  color: #0000ff;
}
```

**Note: `a:hover` MUST come after `a:link` and `a:visited` in the CSS definition in order to be effective! `a:active` MUST come after `a:hover` in the CSS definition in order to be effective! Pseudo-class names are not case-sensitive.**

### All CSS Pseudo Classes

<table class="ws-table-all notranslate">
  <tbody><tr>
    <th style="width:20%">Selector</th>
    <th style="width:20%">Example</th>
    <th>Example description</th>
  </tr>
  <tr>
    <td><a href="/cssref/sel_active.asp">:active</a></td>
    <td class="notranslate">a:active</td>
    <td>Selects the active link</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_checked.asp">:checked</a></td>
    <td class="notranslate">input:checked</td>
    <td>Selects every checked &lt;input&gt; element</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_disabled.asp">:disabled</a></td>
    <td class="notranslate">input:disabled</td>
    <td>Selects every disabled &lt;input&gt; element</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_empty.asp">:empty</a></td>
    <td class="notranslate">p:empty</td>
    <td>Selects every &lt;p&gt; element that has no children</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_enabled.asp">:enabled</a></td>
    <td class="notranslate">input:enabled</td>
    <td>Selects every enabled &lt;input&gt; element</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_firstchild.asp">:first-child</a></td>
    <td class="notranslate">p:first-child</td>
    <td>Selects every &lt;p&gt; elements that is the first child of its parent</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_first-of-type.asp">:first-of-type</a></td>
    <td class="notranslate">p:first-of-type</td>
    <td>Selects every &lt;p&gt; element that is the first &lt;p&gt; element of its parent</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_focus.asp">:focus</a></td>
    <td class="notranslate">input:focus</td>
    <td>Selects the &lt;input&gt; element that has focus</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_hover.asp">:hover</a></td>
    <td class="notranslate">a:hover</td>
    <td>Selects links on mouse over</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_in-range.asp">:in-range</a></td>
    <td class="notranslate">input:in-range</td>
    <td>Selects &lt;input&gt; elements with a value within a specified range</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_invalid.asp">:invalid</a></td>
    <td class="notranslate">input:invalid</td>
    <td>Selects all &lt;input&gt; elements with an invalid value</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_lang.asp">:lang(<i>language</i>)</a></td>
    <td class="notranslate">p:lang(it)</td>
    <td>Selects every &lt;p&gt; element with a lang attribute value starting with "it"</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_last-child.asp">:last-child</a></td>
    <td class="notranslate">p:last-child</td>
    <td>Selects every &lt;p&gt; elements that is the last child of its parent</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_last-of-type.asp">:last-of-type</a></td>
    <td class="notranslate">p:last-of-type</td>
    <td>Selects every &lt;p&gt; element that is the last &lt;p&gt; element of its parent</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_link.asp">:link</a></td>
    <td class="notranslate">a:link</td>
    <td>Selects all unvisited links</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_not.asp">:not(selector)</a></td>
    <td class="notranslate">:not(p)</td>
    <td>Selects every element that is not a &lt;p&gt; element</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_nth-child.asp">:nth-child(n)</a></td>
    <td class="notranslate">p:nth-child(2)</td>
    <td>Selects every &lt;p&gt; element that is the second child of its parent</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_nth-last-child.asp">:nth-last-child(n)</a></td>
    <td class="notranslate">p:nth-last-child(2)</td>
    <td>Selects every &lt;p&gt; element that is the second child of its parent, counting from the last child</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_nth-last-of-type.asp">:nth-last-of-type(n)</a></td>
    <td class="notranslate">p:nth-last-of-type(2)</td>
    <td>Selects every &lt;p&gt; element that is the second &lt;p&gt; element of its parent, counting from the last child</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_nth-of-type.asp">:nth-of-type(n)</a></td>
    <td class="notranslate">p:nth-of-type(2)</td>
    <td>Selects every &lt;p&gt; element that is the second &lt;p&gt; element of its parent</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_only-of-type.asp">:only-of-type</a></td>
    <td class="notranslate">p:only-of-type</td>
    <td>Selects every &lt;p&gt; element that is the only &lt;p&gt; element of its parent</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_only-child.asp">:only-child</a></td>
    <td class="notranslate">p:only-child</td>
    <td>Selects every &lt;p&gt; element that is the only child of its parent</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_optional.asp">:optional</a></td>
    <td class="notranslate">input:optional</td>
    <td>Selects &lt;input&gt; elements with no "required" attribute</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_out-of-range.asp">:out-of-range</a></td>
    <td class="notranslate">input:out-of-range</td>
    <td>Selects &lt;input&gt; elements with a value outside a specified range</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_read-only.asp">:read-only</a></td>
    <td class="notranslate">input:read-only</td>
    <td>Selects &lt;input&gt; elements with a "readonly" attribute specified</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_read-write.asp">:read-write</a></td>
    <td class="notranslate">input:read-write</td>
    <td>Selects &lt;input&gt; elements with no "readonly" attribute</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_required.asp">:required</a></td>
    <td class="notranslate">input:required</td>
    <td>Selects &lt;input&gt; elements with a "required" attribute specified</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_root.asp">:root</a></td>
    <td class="notranslate">root</td>
    <td>Selects the document's root element</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_target.asp">:target</a></td>
    <td class="notranslate">#news:target</td>
    <td>Selects the current active #news element (clicked on a URL containing that anchor name)</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_valid.asp">:valid</a></td>
    <td class="notranslate">input:valid</td>
    <td>Selects all &lt;input&gt; elements with a valid value</td>
  </tr>
  <tr>
    <td><a href="/cssref/sel_visited.asp">:visited</a></td>
    <td class="notranslate">a:visited</td>
    <td>Selects all visited links</td>
  </tr>
</tbody></table>

### All CSS Pseudo Elements

<table class="ws-table-all notranslate">
  <tbody><tr>
    <th style="width:20%">Selector</th>
    <th style="width:20%">Example</th>
    <th>Example description</th>
  </tr>
<tr>
    <td><a href="/cssref/sel_after.asp">::after</a></td>
    <td class="notranslate">p::after</td>
    <td>Insert content after every &lt;p&gt; element</td>
    </tr>
  <tr>
<td><a href="/cssref/sel_before.asp">::before</a></td>
    <td class="notranslate">p::before</td>
    <td>Insert content before every &lt;p&gt; element</td>
    </tr>
<tr>
    <td><a href="/cssref/sel_firstletter.asp">::first-letter</a></td>
    <td class="notranslate">p::first-letter</td>
    <td>Selects the first letter of every &lt;p&gt; element</td>
  </tr>
<tr>
    <td><a href="/cssref/sel_firstline.asp">::first-line</a></td>
    <td class="notranslate">p::first-line</td>
    <td>Selects the first line of every &lt;p&gt; element</td>
  </tr>
<tr>
    <td><a href="/cssref/sel_marker.asp">::marker</a></td>
    <td class="notranslate">::marker</td>
    <td>Selects the markers of list items</td>
  </tr>
<tr>
    <td><a href="/cssref/sel_selection.asp">::selection</a></td>
    <td class="notranslate">p::selection</td>
    <td>Selects the portion of an element that is selected by a user</td>
  </tr>
</tbody></table>

## get similar color

Choose hsl color system to copy a color, then just change the hue.

## Transparency

```css
a:hover {
  opacity: 0.9; /* 0 is transparent, 1 is opaque */
}
```

```css
a:hover {
  background-color: rgba(0, 0, 0, 0.5); /* 0 is transparent, 1 is opaque */
}
```

```css
a:hover {
  background-color: hsla(0, 0%, 0%, 0.5); /* 0 is transparent, 1 is opaque */
}
```

## Lists

- `ul` (unordered list)

```css
ul {
    list-style-type: none;
    text-align: center;
    list-style-position: inside; /* outside is default */
    color: red;
    line-height: 1.5;
    list-style-image: url("https://www.w3schools.com/cssref/sqpurple.png");
    list-style-image: url("../image/sqpurple.png");
    inside; /* this is a shorthand, outside is default */
}
```

- `ol` (ordered list)

```css
ol {
  list-style-type: lower-roman; /* lower-alpha, lower-roman, upper-alpha, upper-roman, etc. */
}
```

### `ol` tag

- example 1:

```html
<ol start="5" reversed>
  <li>nnn</li>
  <li>ddd</li>
  <li>ccc</li>
</ol>
```

output:

> <ol start="5" reversed>
>   <li>nnn</li>
>   <li >ddd</li>
>   <li>ccc</li>
> </ol>

```ol
ol{
    list-style-type: none;
    padding: 0;
}
```

- example 2:

```html
<ol start="5" reversed>
  <li>nnn</li>
  <li value="26">ddd</li>
  <li>ccc</li>
</ol>
```

output:

> <ol start="5" reversed>
>   <li>nnn</li>
>   <li value=26>ddd</li>
>   <li>ccc</li>
> </ol>

```ol
ol{
    list-style-type: none;
    padding: 0;
}
```

### `li`

```css
ul li:nth-child(odd) {
  color: red;
}
```

### Pseudo-elements

```css
::marker {
  color: red;
  font-family: "Times New Roman", Times, serif;
  font-size: 1.5rem;
  content: "👉"; /* This can be svg etc. */
}
```

## `nav`

## `display`

- `display: none;` will remove the element from the DOM.
- `display: block;` will make the element a block element (like `<p>`).
- `display: inline;` will make the element an inline element (like `<span>`).
- `display: inline-block;` will make the element an inline block element (like `<img>`).

```css
ul li {
  display: block;
}

li a:hover {
  background-color: #111;
}
```

With `display: block;`, the whole `li` will be clickable. Not only the text.

### `li:last-child`

```css
li:last-child {
  border-radius: 0 0 5px 5px;
}
```

## block level element vs inline element

In HTML, elements are categorized as either block-level elements or inline elements.

**Block-level elements** form a visible block on a page. They appear on a new line from the content that comes before and after them. Examples include `<div>`, `<h1>` through `<h6>`, `<p>`, and `<form>`.

**Inline elements** do not start on a new line and only take up as much width as necessary. This is in contrast to block-level elements, which occupy the full width available. Examples include `<span>`, `<a>`, `<img>`, and `<button>`.

Here's a simple comparison:

```html
<!-- Block-level elements -->
<div>This is a block-level element.</div>
<p>So is this.</p>

<!-- Inline elements -->
<span>This is an inline element.</span>
<a href="#">So is this.</a>
```

In the above example, each block-level element starts on a new line, while the inline elements do not.

### margin, padding, display with inline elements

In CSS, `margin`, `padding`, and `display` properties behave differently for inline elements compared to block-level elements.

**Margin and Padding:**
For inline elements, `margin` and `padding` are applied differently than block-level elements. Inline elements respect left and right margins and padding, but not top and bottom.

**Display:**
The `display` property determines how an element is displayed. The default value for most elements is either `block` or `inline`.

- `display: inline;` makes the element display inline, like `<span>`.
- `display: block;` makes the element display as a block, like `<div>`.
- `display: inline-block;` is a hybrid of `inline` and `block`. It allows the element to sit inline with other elements, but you can still set width and height values, which isn't possible with `display: inline;`.

Here's an example:

```html
<span
  style="margin: 10px; padding: 10px; display: inline-block; background-color: lightblue;"
  >This is an inline-block element.</span
>
<span
  style="margin: 10px; padding: 10px; display: inline; background-color: lightgreen;"
  >This is an inline element.</span
>
```

In the above example, the first span with `display: inline-block;` respects all the margin and padding values. The second span with `display: inline;` only respects the left and right margin and padding, not the top and bottom.

## menu bar

```css
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  text-align: right;
  background-color: #333;
}

li {
  display: inline-block;
}

li a {
  display: block;
  color: white;
  padding: 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #111;
}
```

## Float

```html
<style>
  .float {
    float: left;
    width: 100px;
    height: 100px;
    margin: 10px;
    background-color: red;
  }
  p {
    margin: 10px;
  }
</style>
<div class="float"></div>
<p>afaewaewfawfeawfaweawefawew</p>
<p>afaewaewfawfeawfaweawefawew</p>
<p>afaewaewfawfeawfaweawefawew</p>
<p>afaewaewfawfeawfaweawefawew</p>
<p>afaewaewfawfeawfaweawefawew</p>
<p>afaewaewfawfeawfaweawefawew</p>
<p>afaewaewfawfeawfaweawefawew</p>
<p>afaewaewfawfeawfaweawefawew</p>
```

- In this case, `p` won't margin with the `div` with class `float`. Because `float` will take the element out of the normal flow. Use `margin` on `.float` instead.
- `clear` would illiminate the effect of `float`.

### `display: flow-root;`

```html
<section>
  <div class="float">Float</div>
  <h3 id="d_h">
    Section Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ipsum,
    alias!
  </h3>
</section>
```

The section doesn't wrap the float div. It's because the float div is out of the normal flow.
There are two ways to fix this

1.  we can use `display: flow-root;` on the container.

```css
.container {
  display: flow-root;
}
```

2. we can use `overflow: auto;` on the container.

```css
.container {
  overflow: auto;
}
```

The first way is better.

##### Explain:

Both `overflow: auto;` and `display: flow-root;` are used to clear floats, but they work in slightly different ways.

**overflow: auto;**
When you set `overflow: auto;` on a container, it means the container will provide a scrollbar if the content overflows the bounds of that container. As a side effect, it also clears floats, meaning it contains the floated elements inside it and prevents them from overlapping the content below the container.

```css
.container {
  overflow: auto;
}
```

**display: flow-root;**
The `display: flow-root;` property creates a new block formatting context, meaning everything inside the container is laid out as a block, and it doesn't interact with anything outside of it. This also effectively clears floats, containing them within the element.

```css
.container {
  display: flow-root;
}
```

The main difference is that `overflow: auto;` can potentially introduce scrollbars, while `display: flow-root;` will not. Therefore, `display: flow-root;` is often a better choice for clearing floats as it has fewer side effects.

## `clear`

```css
.clear {
  clear: both;
}
```

## `colums`

- column-count (number of columns)
- column-width (width of each column)
  > if you set both `column-count` and `column-width`, the browser will choose the one that fits the screen better. This means that column count will be ignored if the width of each column is too wide to fit the screen.
  > shorthand

```css
.container {
  columns: 100px 3; /* width, number of columns */
}
```

```css
.container {
  columns: 4 250px; /* number of columns, width */
}
```

### `column-rule`

```css
.columns {
  columns: 250px 4;
  column-rule: 3px solid #333;
}
```

### `column-gap`

```css
.columns {
  columns: 250px 4;
  column-rule: 3px solid #333;
  column-gap: 20px;
}
```

## Unicode characters

[symbl.cc](https://symbl.cc/)

### Quotation mark

- Heavy Double Turned Comma Quotation Mark Ornament ❝

<table>
  <tbody>
    <tr>
      <td>Unicode Name</td>
      <td>Heavy Double Turned Comma Quotation Mark Ornament</td>
    </tr>
    <tr>
      <td>Unicode Number</td>
      <td style="z-index: 1000">
        <button
          data-goal="copy-character-code-symbol-page"
          type="button"
          class="code js-code-symbl js-symbol-copy"
          data-label="Click to copy"
          data-symbol="U+275D"
        >
          U+275D
        </button>
      </td>
    </tr>
    <tr>
      <td><span class="caps">HTML</span> Code</td>
      <td style="z-index: 100">
        <button
          data-goal="copy-character-code-symbol-page"
          type="button"
          class="code js-code-symbl js-symbol-copy"
          data-label="Click to copy"
          data-symbol="&amp;#10077;"
        >
          &amp;#10077;
        </button>
      </td>
    </tr>
    <tr>
      <td>CSS Code</td>
      <td style="z-index: 10">
        <button
          data-goal="copy-character-code-symbol-page"
          type="button"
          class="code js-code-symbl js-symbol-copy"
          data-label="Click to copy"
          data-symbol="\275D"
        >
          \275D
        </button>
      </td>
    </tr>
    <tr>
      <td>Unicode Block</td>
      <td><a class="link" href="/en/unicode/blocks/dingbats/">Dingbats</a></td>
    </tr>
    <tr>
      <td>Unicode Subblock</td>
      <td>
        <a class="link" href="/en/unicode/blocks/dingbats/#subblock-275B"
          >Punctuation mark ornaments</a
        >
      </td>
    </tr>
    <tr>
      <td>Unicode Version</td>
      <td>1.1 (1993)</td>
    </tr>
  </tbody>
</table>

## `column-span`

The column-span: all; CSS property is used within a multi-column layout. It allows an element to span across all columns when its value is set to all. This can be useful for elements like headings or images that you want to stretch across the column layout.

> Selector calculator is useful.  
> [Specificity Calculator](https://specificity.keegan.st/)

```css
.columns .quote {
  font-size: 3rem;
  text-align: center;
  color: #333;
  column-span: all; /* this is not supported by all browsers */
  margin: 2rem auto 2rem;
}
```

## ` white-space: nowrap;`

```html
<p class="quote">
  &#10077;Where's my rug, man?&#10078;
  <span class="nowrap">&#8212;The dude</span>
</p>
```

The `-` and `The dude` will always be in the same line.

## `position` property

[code](container.html)

CSS property position helps manipulate position of an element in a web page. The properties top, bottom, right, and left are used to control its exact position on the page. They specify the offsets of an element from its edges

<ul class="list">
   <li><p><b>static −</b> The element is positioned according to the default or normal flow of the page. So if we set left/right/top/bottom/z-index, then there will be no effect on that element.</p></li>
   <li><p><b>relative −</b> The element's orginial position is according to normal flow of the page just like <b>static</b> value. But now left/right/top/bottom/z-index will work. The positional properties push the element from the original position in that direction.</p></li>
   <li><p><b>absolute −</b> The element is completely removed from the document flow. It is then positioned with respect to its containing block, and its edges are placed using the side-offset properties. An absolutely positioned element may overlap other elements, or be overlapped by them.</p></li>
   <li><p><b>fixed −</b> The element's fixed positioning is just like absolute positioning, except the containing block of a fixed element is always the viewport. Here the element is totally removed from the document's flow and does not have a position relative to any part of the document. </p></li>
   <li><p><b>sticky −</b> The element sticks to the top of its nearest positioned ancestor that has a "scrolling mechanism" .</p></li>
</ul>

### Set an element way off the screen

```css
.absolute {
  background-color: blue;
  position: absolute;
  top: 0;
  left: -10000px; /* this is a hack */
  z-index: 1;
}
```

## `z-index` property

The z-index property specifies the stack order of an element. An element with greater stack order is always in front of an element with a lower stack order.

## `scroll-behavior: smooth;`

Scroll smoothly when click:

```html
<section id="one">
  <header class="blue">Header One</header>
  <h2>One</h2>
</section>
<section id="two">
  <header class="red">Header Two</header>
  <h2>Two</h2>
</section>
<section id="three">
  <header class="green">Header Three</header>
  <h2>Three</h2>
</section>
<footer>
  <a href="#one">One</a>
  <a href="#two">Two</a>
  <a href="#three">Three</a>
</footer>
```

# Grid Layout

- `display: grid;`
- `grid-auto-flow: column;`
- `grid-template-columns: 200px 1fr 2fr;`
- `grid-template-columns: repeat(4,1fr 2fr);`
  > row as so.
- `grid-column-start: 1;` `grid-column-end: 4;` and `grid-column: 1/4;`
- `grid-row-start: 1;` `grid-row-end: 3;` and `grid-row: 1/3;`
- `align-content: start;` of grid layout
- `align-content: center;` `justify-content: center;` and `place-content: end center;` or `place-content: center`
- `grid-template-areas`

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: sans-serif;
  min-height: 100vh;

  display: grid;
  grid-template-columns: repeat(9, 1fr);
  grid-auto-rows: 75px auto 75px;
  grid-template-areas:
    "hd hd hd hd hd hd hd hd hd"
    "mn mn mn mn mn mn mn sb sb"
    "ft ft ft ft ft ft ft ft ft";
  gap: 1rem;
}
.el {
  background-color: rebeccapurple;
  color: #fff;
  display: grid;
  place-content: center;
}
.header {
  grid-area: hd;
}

.sidebar {
  grid-area: sb;
  background-color: #00f;
}
.footer {
  grid-area: ft;
}

.container {
  min-height: 400px;
  display: grid;
  /* grid-auto-flow: column; */
  /* grid-template-columns: 200px 1fr 2fr; */
  grid-template-columns: repeat(2, 1fr 2fr);
  /* grid-auto-rows: 200px; */
  grid-auto-rows: minmax(150px, auto);
  /* grid-template-rows: repeat(2,1fr 2fr); */
  row-gap: 1em;
  /* column-gap: 1em; */
  /* gap: 1em 0.5em; */
  gap: 1em;
  grid-area: mn;
}
.box {
  background-color: #000;
  color: #fff;
  font-size: 2rem;
  padding: 0.5rem;
}
.box:first-child {
  background-color: #00f;
  /* grid-column-start: 1;
        grid-column-end: 4;
        grid-row-start: 1;
        grid-row-end: 3; */
  grid-column: 1/4;
  grid-row: 1/3;

  display: grid;
  /* align-content: center;
        justify-content: center; */
  place-content: center;
}
.box:nth-child(2) {
  background-color: purple;
  grid-column: 1/5;
  grid-row: 3/4;
}
```

### Practice

[**cssgridgarden**](http://cssgridgarden.com/)

## Images

- `<img>` is inline tag
- `background-image: url('img/acg.gy_04.jpg');`
- `background-repeat: no-repeat;`
- `background-position`
  > which part of the image
- `background-size`
  > [Try it](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size)
- `background-image: url("img/acg.gy_10.jpg"),linear-gradient(to left, black, purple, #fff);`
  > also `background-image: liner-gradient()`, this is a rainbow.

### Background color advanced

Set background image in parent container, then in child box, set background color(better use hsl system: hue, saturation, lightness, transparency), then you can optimize the emphasize of the background image

```css
.container {
  background-color: rgb(251, 210, 156);
  background-image: url("img/acg.gy_04.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}
.hero {
  border-bottom: 2px solid #000;
  padding: 20px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  gap: 30px;

  background-color: hsla(15, 100%, 31%, 0.17);
  /* background-color: rgb(251, 210, 156);
        background-image: url("img/acg.gy_04.jpg");
        background-repeat: no-repeat;
        background-size: cover;*/
}
```
