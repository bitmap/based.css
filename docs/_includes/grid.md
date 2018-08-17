## Grid
---

Based comes with an extensive flexbox-based grid system. There are 8 columns by default, but if you prefer 12, 16 or whatever, you can change the `$grid-columns` variable in Based's config file.

### Wrapper
`.wrap`
The `wrap` class wraps all elements at a maximum width, determined by you. It is horizontally centered. It's not required, but it does keep your grid nice and tidy looking on larger screens. The maximum width of the wrapper out of the box is `64rem` (or `1024px`).

### Rows
`.row` or `.flex`
The `row` class *is required*. The row class wraps all of you columns. It has a few properties that enable the flexbox features, and has a few extensions that allow you to change the behavior of you columns. It has a negative margin to make sure that column padding is retained. Sometimes, however, this negative margin is not desirable. That's why there's a secret `flex` class that enables all the flexbox stuff. Use it wisely.

### Columns
`.col + .span-[n]@[bp]`
The `col` class defines a block element as a column. Columns are the meat of the grid. There's no restriction on the type of content you can put inside a column. They behave how you expect them to, and there's a grid for each breakpoint. Simply specify the breakpoint and the number of columns you want to span. For example `span-6@lg` will span across six columns at the large breakpoint.

### Responsive
Column widths _start at mobile and scale to desktop_. For example, a div with the classes `span-8 span-6@md` the `span-6@md` breakpoint will override the `span-8` breakpoint on medium-sized screens. Each tier of classes scales up from mobile tiers, meaning if you plan on setting the same widths for `lg` and `sm`, you only need to specify `sm`. When in doubt, mobile-first.

---
### Basic Examples

#### Naked
<div class="row">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>

#### Two column
<div class="row">
  <div class="col span-6"></div>
  <div class="col span-2"></div>
</div>

#### Half and half
<div class="row">
  <div class="col span-4"></div>
  <div class="col span-4"></div>
</div>

#### Three equal columns
<div class="row">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>

#### Three unequal columns
<div class="row">
  <div class="col span-2"></div>
  <div class="col span-4"></div>
  <div class="col span-2"></div>
</div>


### Nesting
Nesting is easy—just put a row of columns within an existing column. On mobile these columns and their nested columns will stack (layout is exagerated in these examples, it won't stack so tall).

<div class="row">
  <div class="col span-5">(parent)
    <div class="row">
      <div class="col span-4">(child) </div>
      <div class="col span-4">(child) </div>
    </div>
  </div>
  <div class="col span-3">(parent, no child) </div>
</div>


### Mixing breakpoints
The Based grid system has four tiers of classes: default (phones), `@sm` (tablets), `@md` (small desktop), and `@lg` (full-width). You can combine these classes to create more flexible layouts.

<div class="row">
  <div class="col span-8 span-4@lg"></div>
  <div class="col span-8 span-4@lg"></div>
</div>
<div class="row">
  <div class="col span-6 span-2@md"></div>
  <div class="col span-8 span-6@md"></div>
</div>
<div class="row">
  <div class="col span-8 span-6@sm span-4@lg"></div>
  <div class="col span-8 span-2@sm span-4@lg"></div>
</div>


### Offset
Offset `n` columns left. This also offsets from any preceding siblings, adjacent siblings will retain their flow.

<div class="row">
  <div class="col span-7 offset-1"></div>
</div>
<div class="row">
  <div class="col span-3 offset-1"></div>
  <div class="col span-3 offset-1"></div>
</div>
<div class="row">
  <div class="col span-3 offset-3"></div>
  <div class="col span-2"></div>
</div>


### Push / Pull
By default, _all coulmns read left to right_ in the order they appear in the DOM. However, on some breakpoints you may want an element on the the right and others on the left. There are ways for flexbox to handle this (see Order), but `push` and `pull` can achieve the same result. These work a bit like Offset, but don't apply margins so you can overlap colums.

**Be advised**, using these class can have adverse effects on layout, and weird stuff can happen if you're not careful.

<div class="row">
  <div class="col span-4 push-4">(1<sup>st</sup> in DOM) </div>
  <div class="col span-4 pull-4">(2<sup>nd</sup> in DOM) </div>
</div>

### Aligning Columns
Adding these classes to the `row` allows flexbox to work its magic. `align-[whatever]` refers to the _vertical alignment_ inside the container. `justify-[whatever]` controls the _horizontal alignment_.

They can be mixed and matched in lieu of the push/pull classes to align columns.

#### align-end justify-start
<div class="row align-end justify-start" style="height: 128px;">
  <div class="col span-3"></div>
  <div class="col span-3"></div>
</div>

#### align-start justify-center
<div class="row align-start justify-center" style="height: 128px;">
  <div class="col span-3"></div>
  <div class="col span-3"></div>
</div>

#### align-center justify-end
<div class="row align-center justify-end" style="height: 128px;">
  <div class="col span-3"></div>
  <div class="col span-3"></div>
</div>

Adding `align-start`, `align-center`, and `align-end` to a `col` element applies the alignment individually for more advanced layouts. Columns appear in the same order as the DOM. _These override the alignment class on the parent_, so be careful.

<div class="row" style="height: 128px;">
  <div class="col span-2 align-start"></div>
  <div class="col span-3 align-end"></div>
  <div class="col span-3 align-center"></div>
</div>

### Aligning Rows
You can align everything using the `content-[whatever]` classes.

#### content-start
<div class="row content-start" style="height: 256px;">
  <div class="col span-2"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-1"></div>
  <div class="col span-4"></div>
</div>

#### content-center
<div class="row content-center" style="height: 256px;">
  <div class="col span-2"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-1"></div>
  <div class="col span-4"></div>
</div>

#### content-end
<div class="row content-end" style="height: 256px;">
  <div class="col span-2"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-1"></div>
  <div class="col span-4"></div>
</div>


### Space
`justify-space-between`, `justify-space-around`, and `justify-space-evenly`  help space out elements by filling the space around or between elements. You must apply this class to the `row`.
#### justify space-between
<div class="row justify-space-between">
  <div class="col span-2"></div>
  <div class="col span-2"></div>
  <div class="col span-2"></div>
</div>

#### justify-space-around
<div class="row justify-space-around">
  <div class="col span-2"></div>
  <div class="col span-2"></div>
  <div class="col span-2"></div>
</div>

#### justify-space-evenly
<div class="row justify-space-evenly">
  <div class="col span-2"></div>
  <div class="col span-2"></div>
  <div class="col span-2"></div>
</div>

You can also apply this to columns that wrap into multiple rows using the `content-space-between` and `content-space-around` classes.

#### content-space-between
<div class="row content-space-between" style="height: 256px;">
  <div class="col span-2"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-1"></div>
  <div class="col span-4"></div>
</div>

#### content-space-around
<div class="row content-space-around" style="height: 256px;">
  <div class="col span-2"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-3"></div>
  <div class="col span-1"></div>
  <div class="col span-4"></div>
</div>

### Order
By default the `order` property is `0`, so elements stack as as expected. The `order-0` through `order-12` change the order to `0` through `12`, respectively.
<div class="row">
  <div class="col span-4 order-8">(first in DOM)</div>
  <div class="col span-4 order-4">(last in DOM)</div>
</div>

### Reverse Columns
Reverse the order of the columns by adding `row--reverse` to the `row`.
<div class="row row--reverse">
  <div class="col span-2">[1] </div>
  <div class="col span-2">[2] </div>
  <div class="col span-2">[3] </div>
  <div class="col span-2">[4] </div>
</div>

### Stack Columns
You can stack columns using the `row--stack` class to the `row`.

<div class="row row--stack">
  <div class="col span-4 push-3"></div>
  <div class="col span-2"></div>
  <div class="col span-4 offset-1"></div>
</div>

## Tricks
Based's grid has a few neat tricks thanks to Flexbox. You can achieve dynamic layouts without the need for some of the more advanced column alignment classes detailed above.

### Auto X-Margins
The `mx-auto` class horizontally centers whatever column you have in there.
<div class="row">
  <div class="col span-6 mx-auto"></div>
</div>

Very useful, and adding more columns will automatically calculate offsets between columns. This can have unintended consequences, so use it wisely.
<div class="row">
  <div class="col span-2"></div>
  <div class="col span-2 mx-auto"></div>
  <div class="col span-2"></div>
</div>

Another neat trick is to use the `ml-auto` and `mr-auto` class to simulate floats.
<div class="row">
  <div class="col span-3 mr-auto"></div>
  <div class="col span-3 ml-auto"></div>
</div>

### Auto-Y Margins
By giving the `row` container some form of height, you can use the `my-auto` classes to vertically center.
<div class="row" style="height: 128px;">
  <div class="col span-6 my-auto"></div>
</div>

You can create some very flexible layouts by combining this with the x-margin classes.
<div class="row" style="height: 128px;">
  <div class="col span-3 mr-auto"></div>
  <div class="col span-4 my-auto"></div>
</div>

### The Holy Grail
The `m-auto` class applies an auto margin around the entire column. On a `row` with a height applied to it, you can achieve the holy grail of CSS layouts, without and absolute positioning or transform tricks.
<div class="row" style="height: 128px;">
  <div class="col span-5 m-auto"></div>
</div>
