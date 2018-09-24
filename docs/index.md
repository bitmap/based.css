# Based.css

Based is a barebones CSS framework for prototype or production.

---

### Philosophy
Based is strictly barebones CSS. All of the included classes are designed to offer the least amount of assumptions about what your site looks like. Based doesn't normalize or reset any browser styles besides setting `box-sizing: border-box` on literally everything.

Based (by default) strives to compliment an 8pt grid system. This ensures some form of vertical rhythm in your designs. You're welcome to reconfigure this.

### Mobile First
Based is fully responsive. The base class names are for the single, naked, mobile breakpoint and scale up forever. You can override the classby appending `@sm`, `@md`, `@lg`, and `@xl` suffix. For example, `display-none` can be overridden by `display-block@sm` at the small breakpoint, which can be overridden by `display-inline@lg` at the large breakpoint.

You get it. This is most useful with the grid, as you'll see.

| Breakpoints    | min-width (@ base 16) | min-width (rem)
| :------------- | :-------------------- | :-----
| `@sm`          | 544px                 | 32rem
| `@md`          | 768px                 | 48rem
| `@lg`          | 1024px                | 64rem
| `@xl`          | 1280px                | 80rem

### Root Sizing
You'll probably notice things look different if you've set the font-size on your root selector (`:root` or `html`) to anything other than `16px`. Based is designed to scale from this unit by liberally using `rem` and `%` values for sizing. Size set on the `<body>` is ignored, however.

If you would like to use pixel units instead, you can override the `$based_spacing` value and it will scale form that.

### Customization
Based has pretty basic defaults, so you'll likely want to tweak these things first based on your designs. Based's defaults can be referenced in `src/_config`. After importing `based.scss` in your project, you can modify any of the `$based_*` variables to suit your needs.

| Variable                    | Type                  | Default
| :-------------------------- | :-------------------- | :-----
| `$based_spacing`            | Unit                  | 1rem
| `$based_spacing-multiplier` | Number                | 4
| `$based_spacing-sides`      | Map                   | (all, x, y, t, l, b, r)
| `$based_grid-breakpoints`   | Map                   | (sm, md, lg, xl)
| `$based_grid-columns`       | Number                | 8
| `$based_grid-max-width`     | Unit                  | 64rem
| `$based_grid-gutter-width`  | Unit                  | 1rem
