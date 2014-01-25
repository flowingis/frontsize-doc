#State

State CSS selectors should be used in `class` attribute in the *HTML elements* on you page views. If you want to know more on how they are thought read how it work [SMACSS state](http://smacss.com/book/state), will be very helpful.

The contents of this page are located in `core/state.less`.

###Page index

- [Containers](#containers)
- [Images](#images)
- [Interaction](#interaction)
- [Lists](#lists)
- [Miscellaneous](#miscellaneous)
- [Navigation](#navigation)
- [Positioning](#positioning)
- [Spacing](#spacing)
- [Tables](#tables)
- [Text](#text)

##Containers

Selector name	| Description
-|-
`.almost`		| Sets `width` *CSS property* to `75%`
`.auto`			| Sets `width` *CSS property* to `auto`
`.block`		| Sets `display` *CSS property* to `block`
`.box`			| Sets `overflow` *CSS property* to `auto`
`.visible`		| Sets `overflow` *CSS property* to `visible`
`.cut`			| Sets `overflow` *CSS property* to `hidden`
`.fill`			| Sets `width` *CSS property* to `100%`
`.full`			| Sets `box-sizing`, `float` and `padding` *CSS properties* as a **Frontsize** responsive column
`.half`			| Sets `width` *CSS property* to `50%`
`.inline`		| Sets `display` *CSS property* to `inline-block` and `width` to `auto`
`.little`		| Sets `width` *CSS property* to `25%`
`.wrap`			| Sets `box-sizing` *CSS property* to `border-box`
`.wrap-content`	| Sets `box-sizing` *CSS property* to `content-box`

##Images

Selector name	| Description
-|-
`.fluid`		| Makes an image responsive, if the container is more wider than the image it will reach it's max width without stretch more
`.fluid.fill`	| Makes an image responsive, if the container is more wider than the image it will fill the container width by stretching it mantaining it's original proportions
`.not-fluid`	| Makes an image non-responsive, `width` and `height` *CSS properties* are be set to `auto`

##Interaction

Selector name	| Description
-|-
`.pointer`		| Sets `cursor` *CSS property* to `pointer`
`.selected`		| Sets `cursor` *CSS property* to `default`
`.faded`		| Sets `opacity` *CSS property* to `@state-faded-opacity` located in `frontsize/app.less`
`.disabled`		| Sets `cursor` to `default` and `opacity` *CSS property* to `@state-disabled-opacity` located in `frontsize/app.less`
`.invisible`	| Sets `opacity` *CSS property* to `0`
`.hidden`		| Sets `display` *CSS property* to `none`

##Lists

Selector name			| Description
-|-
`.no-list-style`		| Sets the `list-style-type` *CSS property* to `none`

##Miscellaneous

Selector name	| Description
-|-
`.commas`		| Append `, ` after every children *HTML element* except the last one.
`.hookable`		| Sets `transition` *CSS property* to be tweenable for `top`, `right`, `bottom` and `left`
`.flip`			| Makes an *HTML element* ready to be 3D flipped
`.flip.reverse`	| Makes an *HTML element* flipped to to it's backface, when an element it's flippet, it's invisible

##Navigation

Selector name			| Description
-|-
`.nav`					| Perpare an `ul` *HTML element* list to be used as navigation menu
`.nav.inline`			| Sets `ul` *HTML element* list to be used as inline navigation menu
`.nav.vertical`			| Sets `ul` *HTML element* list to be used as vertical navigation menu

##Positioning

Selector name			| Description
-|-
`.gain-margin`			| Sets `margin-left` and `margin-right` *CSS properties* to `-@horizontal-padding` located in `frontsize/app.less`
`.to-center`			| Sets `margin-left` and `margin-right` *CSS properties* to `auto`
`.to-left`				| Sets `float` *CSS property* to `left`
`.to-right`				| Sets `float` *CSS property* to `right`
`.clear`				| Sets `clear` *CSS property* to `both`
`.relative`				| Sets `position` *CSS property* to `relative`
`.move-bottom-left`		| Sets `position` *CSS property* to `absolute`, sets `bottom` and `left` to `0px`
`.move-bottom-right`	| Sets `position` *CSS property* to `absolute`, sets `bottom` and `right` to `0px`
`.move-top-left`		| Sets `position` *CSS property* to `absolute`, sets `top` and `left` to `0px`
`.move-top-right`		| Sets `position` *CSS property* to `absolute`, sets `top` and `right` to `0px`
`.fixed`				| Sets `position` *CSS property* to `fixed`
`.fixed.cover`			| Sets `position` *CSS property* to `fixed`, sets `top`, `right`, `bottom` and `left` to `0px`
`.fixed.to-top`			| Sets `position` *CSS property* to `fixed` and sets `top` to `0px`
`.fixed.to-right`		| Sets `position` *CSS property* to `fixed` and sets `right` to `0px`
`.fixed.to-bottom`		| Sets `position` *CSS property* to `fixed` and sets `bottom` to `0px`
`.fixed.to-left`		| Sets `position` *CSS property* to `fixed` and sets `left` to `0px`

##Spacing

Selector name			| Description
-|-
`.with-padding`			| Sets `padding` *CSS property* to `@vertical-padding @horizontal-padding` located in `frontsize/app.less`
`.horizontal-padding`	| Sets `padding-left` and `padding-right` *CSS properties* to `@horizontal-padding` located in `frontsize/app.less`
`.vertical-padding`		| Sets `padding-top` and `padding-bottom` *CSS properties* to `@vertical-padding` located in `frontsize/app.less`
`.top-padding`			| Sets `padding-top` *CSS property* to `@vertical-padding` located in `frontsize/app.less`
`.bottom-padding`		| Sets `padding-bottom` *CSS property* to `@vertical-padding` located in `frontsize/app.less`
`.left-padding`			| Sets `padding-left` *CSS property* to `@horizontal-padding` located in `frontsize/app.less`
`.right-padding`		| Sets `padding-right` *CSS property* to `@horizontal-padding` located in `frontsize/app.less`
`.no-padding`			| Sets `padding` *CSS property* to `0`
`.no-top-padding`		| Sets `padding-top` *CSS property* to `0`
`.no-bottom-padding`	| Sets `padding-bottom` *CSS property* to `0`
`.no-vertical-padding`	| Sets `padding-top` and `padding-bottom` *CSS properties* to `0`

Selector name			| Description
-|-
`.with-margin`			| Sets `margin` *CSS property* to `@vertical-padding @horizontal-padding` located in `frontsize/app.less`
`.horizontal-margin`	| Sets `margin-left` and `margin-right` *CSS properties* to `@horizontal-padding` located in `frontsize/app.less`
`.vertical-margin`		| Sets `margin-top` and `margin-bottom` *CSS properties* to `@vertical-padding` located in `frontsize/app.less`
`.top-margin`			| Sets `margin-top` *CSS property* to `@vertical-padding` located in `frontsize/app.less`
`.bottom-margin`		| Sets `margin-bottom` *CSS property* to `@vertical-padding` located in `frontsize/app.less`
`.left-margin`			| Sets `margin-left` *CSS property* to `@horizontal-padding` located in `frontsize/app.less`
`.right-margin`			| Sets `margin-right` *CSS property* to `@horizontal-padding` located in `frontsize/app.less`
`.no-margin`			| Sets `margin` *CSS property* to `0`
`.no-top-margin`		| Sets `margin-top` *CSS property* to `0`
`.no-bottom-margin`		| Sets `margin-bottom` *CSS property* to `0`
`.no-vertical-margin`	| Sets `margin-top` and `margin-bottom` *CSS properties* to `0`

##Tables

Selector name		| Description
-|-
`.table`			| Makes the *HTML element* a `table` element, which also set first level children elements as `table-row` and second level elements as `table-cell`, the table `width` will be set to `100%` and `vertical-align` to `middle`
`.table-top`		| Makes the *HTML element* a `table` element, which also set first level children elements as `table-row` and second level elements as `table-cell`, the table `width` will be set to `100%` and `vertical-align` to `top`
`.inline-table`		| Makes the *HTML element* a `table` element, which also set first level children elements as `table-row` and second level elements as `table-cell`, the table `width` will be set to `auto` and `vertical-align` to `middle`
`.cell`				| Makes the *HTML element* a `table-cell` with `vertical-align` to `middle`
`.cell-top`			| Makes the *HTML element* a `table-cell` with `vertical-align` to `top`
`.cell-bottom`		| Makes the *HTML element* a `table-cell` with `vertical-align` to `bottom`

##Text

Selector name		| Description
-|-
`.bold`				| Sets `font-weight` *CSS property* to `bold`
`.no-wrap`			| Sets `white-space` *CSS property* to `nowrap`
`.capitalize`		| Sets `text-transform` *CSS property* to `capitalize`
`.text-center`		| Sets `text-align` *CSS property* to `centered`
`.text-justify`		| Sets `text-align` *CSS property* to `justify`
`.text-right`		| Sets `text-align` *CSS property* to `right`
`.text-left`		| Sets `text-align` *CSS property* to `left`
`.underline`		| Sets `text-decoration` *CSS property* to `underline`
`.lowercase`		| Sets `text-transform` *CSS property* to `lowercase`
`.uppercase`		| Sets `text-transform` *CSS property* to `uppercase`
`.line-through`		| Sets `text-decoration` *CSS property* to `line-through`
`.unselectable`		| Sets `user-select` *CSS property* to `none`
`.line-height`		| Sets `line-height` *CSS property* to `@font-line-height` located in `frontsize/app.less`
`.no-line-height`	| Sets `line-height` *CSS property* to `0`
`.font-sans`		| Sets `font-family` *CSS property* to `@font-sans` defined in `app.less`
`.font-serif`		| Sets `font-family` *CSS property* to `@font-serif` defined in `app.less`
`.font-monospace`	| Sets `font-family` *CSS property* to `@font-monospace` defined in `app.less`
`.font-heading`		| Sets `font-family` *CSS property* to `@font-heading` defined in `app.less`
`.font-small`		| Sets `font-family` *CSS property* to `@font-small` defined in `app.less`