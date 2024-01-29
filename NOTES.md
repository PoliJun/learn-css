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
