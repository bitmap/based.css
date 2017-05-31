## Spacing
---

Spacing with margin and padding can be achieved with the `m` and `p` prefixed classes. By default, spacing is based on the font size of the root (`html`) element using `rem` units.

Margin classes start with `.m`. The class for 2rem margin on each side is `.m2`. You can specify two sides with `x` or `y`, so 2rem on the top and bottom only is `.my2`. Margin also has the unique `-auto` suffix for auto-margins. For example, horizontally centering block elements can easily be achieved with the `mx-auto` class.


| Class            | Prop(s)                     |
| :-------------   | :------------------------   |
| `.m`             | margin                      |
| `.my`            | margin-top, margin-bottom   |
| `.mx`            | margin-left, margin-right   |
| `.mt`            | margin-top                  |
| `.mb`            | margin-bottom               |
| `.ml`            | margin-left,                |
| `.mr`            | margin-right                |

Padding works nearly the same, but are prefixed with `.p`. for example `.pb3` adds 3rem padding to the bottom of the element. The `-auto` suffix does not work here, for obvious reasons.

| Class            | Prop(s)                     |
| :-------------   | :-------------------------- |
| `.p`             | padding                     |
| `.py`            | padding-top, padding-bottom |
| `.px`            | padding-left, padding-right |
| `.pt`            | padding-top                 |
| `.pb`            | padding-bottom              |
| `.pl`            | padding-left,               |
| `.pr`            | padding-right               |


### Responsive Spacing
The spacing classes also correspond with the grid breakpoints. The base classes are mobile-first. For example, if you want to use 1rem top and bottom padding on mobile but 4rem padding at desktop breakpoints, you would apply `class="py1 py4@lg"` to the element.
