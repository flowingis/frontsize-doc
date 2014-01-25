#Cross browser property mixins

###Page index

- [Border](#border)
- [Filter](#filter)
- [Placeholder](#placeholder)
- [Text](#text)
- [2D Transform](#2d-transform)
- [3D Transform](#3d-transform)
- [Interaction](#interaction)
- [Image](#image)
- [Background image](#background-image)
- [Simple transform](#simple-transform)
- [Print](#print)

The contents of this page are located in `core/prefixes.less`.

##Border

Property mixin			| Default value			| Description
--- | --- | ---
`.border-image`			| *none*				| [Border image at W3Schools](http://www.w3schools.com/cssref/css3_pr_border-image.asp)
`.border-radius`		| `6px`					| [Border radius at W3Schools](http://www.w3schools.com/cssref/css3_pr_border-radius.asp)
`.outline-radius`		| `6px`					| [Outline radius at CSS3 info](http://www.css3.info/preview/outline/)

##Box

Property mixin			| Default value					| Description
--- | --- | ---
`.displayBox`			| No params expected			| [Display box property at W3Schools](http://www.w3schools.com/cssref/css3_pr_box-align.asp)
`.box-align`			| `stretch`						| [Box align at W3Schools](http://www.w3schools.com/cssref/css3_pr_box-align.asp)
`.box-direction`		| `normal`						| [Box direction at W3Schools](http://www.w3schools.com/cssref/css3_pr_box-direction.asp)
`.box-flex`				| `0.0`							| [Box flex at W3Schools](http://www.w3schools.com/cssref/css3_pr_box-flex.asp)
`.box-ordinal-group`	| `1`							| [Box ordinal group at W3Schools](http://www.w3schools.com/cssref/css3_pr_box-ordinal-group.asp)
`.box-orient`			| `inline-axis`					| [Box orient at W3Schools](http://www.w3schools.com/cssref/css3_pr_box-orient.asp)
`.box-pack`				| `inline-axis`					| [Box pack at W3Schools](http://www.w3schools.com/cssref/css3_pr_box-pack.asp)
`.box-sizing`			| `content-box`					| [Box sizing at W3Schools](http://www.w3schools.com/cssref/css3_pr_box-sizing.asp)
`.box-shadow`			| `0px 0px 1px rgba(0,0,0,.3)`	| [Box shadow at W3Schools](http://www.w3schools.com/cssref/css3_pr_box-shadow.asp)

######Box shadow example

```less
/* in app.less file */
@use-css-prefix: true;

/* in your view_name.less file or inside layout folder */
.css-selector {
	.box-shadow(0px 2px 4px rgba(0,0,0,0.3));
}
```

While you set `@use-css-prefix` to `true` every CSS3 mixin will be exported with all CSS3 native browsers prefixes.

**CSS Result**

```css
.css-selector {
	box-shadow: 0px 2px 4px rgba(0,0,0,0.3);
	-webkit-box-shadow: 0px 2px 4px rgba(0,0,0,0.3);
	-khtml-box-shadow: 0px 2px 4px rgba(0,0,0,0.3);
	-moz-box-shadow: 0px 2px 4px rgba(0,0,0,0.3);
	-ms-box-shadow: 0px 2px 4px rgba(0,0,0,0.3);
	-o-box-shadow: 0px 2px 4px rgba(0,0,0,0.3);
}

```

Just set `@use-css-prefix` to `false` to keep the standard CSS3 property names only.

**LESS usage example**

```less
/* in app.less file */
@use-css-prefix: false;

/* in your view_name.less file or inside layout folder */
.css-selector {
	.box-shadow(0px 2px 4px rgba(0,0,0,0.3));
}
```

While you set `@use-css-prefix` to `true` every CSS3 mixin will be exported with all CSS3 native browsers prefixes.

**CSS Result**

```css
.css-selector {
	box-shadow: 0px 2px 4px rgba(0,0,0,0.3);
}

```

This works for all CSS3 mixins.

##Filter

Property mixin				| Default value								| Description
--- | --- | ---
`.filter`					| *none*									| [Filter at David Walsh website](http://davidwalsh.name/css-filters)
`.blur`						| `0`										| [CSS3 filters at David Walsh website](http://davidwalsh.name/demo/css-filters.php)

##Placeholder

Property mixin				| Default value								| Description
--- | --- | ---
`.globalPlaceholder`		| `@color:#999999, @focused:#CCCCCC`		| Sets the color of the `input-placeholder` *CSS* property globally
`.input-placeholder`		| `@color:#999999, @focused:#CCCCCC`		| Sets the color of the `input-placeholder` *CSS* property to a specific selector

##Text

Property mixin			| Default value											| Description
--- | --- | ---
`.globalSelection`		| `@text-color:inherit, @background-color:inherit`		| Sets the color of the `::selection` of all texts and their color with *CSS* pseudo element selector
`.selection`			| `@color:#999999, @focused:#CCCCCC`					| Sets the color of the `::selection` of a text and it's color with *CSS* pseudo element selector
`.font-smoothing`		| `antialiased`											| [Font smoothing on Usability Post](http://www.usabilitypost.com/2010/08/26/font-smoothing/)
`.column-count`			| `auto`												| [Column count at W3Schools](http://www.w3schools.com/cssref/css3_pr_column-count.asp)
`.column-gap`			| `normal`												| [Column gap at W3Schools](http://www.w3schools.com/cssref/css3_pr_column-gap.asp)
`.column-rule`			| `medium none black`									| [Column rule at W3Schools](http://www.w3schools.com/cssref/css3_pr_column-rule.asp)
`.column-span`			| `1`													| [Column span at W3Schools](http://www.w3schools.com/cssref/css3_pr_column-span.asp)
`.column-width`			| `antialiased`											| [Column width at W3Schools](http://www.w3schools.com/cssref/css3_pr_column-width.asp)
`.columns`				| `auto auto`											| [Columns at W3Schools](http://www.w3schools.com/cssref/css3_pr_columns.asp)
`.hyphens`				| `none`												| [Hypens at W3Schools](http://www.w3schools.com/cssref/css3_pr_resize.asp)
`.text-overflow`		| `ellipsis`											| [Text overflow at W3Schools](http://www.w3schools.com/cssref/css3_pr_text-overflow.asp)
`.text-fill-color`		| `transparent`											| [Text fill color at Quirksmode](http://www.quirksmode.org/css/stroke.html)
`.text-stroke`			| `black 1px`											| [Text stroke at Quirksmode](http://www.quirksmode.org/css/stroke.html)
`.text-stroke-color`	| `black`												| [Text stroke color at Quirksmode](http://www.quirksmode.org/css/stroke.html)
`.text-stroke-width`	| `1px`													| [Text stroke width at Quirksmode](http://www.quirksmode.org/css/stroke.html)

##2D Transform

Property mixin			| Default value							| Description
--- | --- | ---
`.transform`			| `none`								| [Transform at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.matrix`				| `0,0,0,0,0,0;`						| [Matrix at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.matrix3d`				| `0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0;`	| [Matrix3d at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.translate`			| `0,0;`								| [Translate at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.translate3d`			| `0,0,0;`								| [Translate3d at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.translateX`			| `0`									| [TranslateX at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.translateY`			| `0`									| [TranslateY at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.translateZ`			| `0`									| [TranslateZ at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.scale`				| `0`									| [Scale at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.scaleX`				| `0`									| [ScaleX at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.scaleY`				| `0`									| [ScaleY at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.scaleZ`				| `0`									| [ScaleZ at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.rotate`				| `0`									| [Rotate at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.rotateX`				| `0`									| [RotateX at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.rotateY`				| `0`									| [RotateY at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.rotateZ`				| `0`									| [RotateZ at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.rotate3d`				| `0,0,0,0deg;`							| [Rotate3d at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.skew`					| `0deg,0deg`							| [Skew at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.skewX`				| `0deg`								| [SkewX at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.skewY`				| `0deg`								| [SkewY at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)
`.perspective`			| `0`									| [Perspective at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform.asp)

##3D Transform

Property mixin						| Default value						| Description
--- | --- | ---
`.transform-style`					| `flat`							| [Transaform style at W3Schools](http://www.w3schools.com/cssref/css3_pr_transform-style.asp)
`.backface-visibility`				| `visible`							| [Backface visibility at W3Schools](http://www.w3schools.com/cssref/css3_pr_backface-visibility.asp)

##Transition

Property mixin						| Default value						| Description
--- | --- | ---
`.transition`						| `0.3s ease-in-out initial`		| [Transition style at W3Schools](http://www.w3schools.com/cssref/css3_pr_transition.asp)
`.transition-delay`					| `0.5s`							| [Transition delay at W3Schools](http://www.w3schools.com/cssref/css3_pr_transition-delay.asp)
`.transition-duration`				| `0.5s`							| [Transition duration at W3Schools](http://www.w3schools.com/cssref/css3_pr_transition-duration.asp)
`.transition-property`				| `all`								| [Transition property at W3Schools](http://www.w3schools.com/cssref/css3_pr_transition-property.asp)
`.transition-timing-function`		| `all`								| [Transition timing function at W3Schools](http://www.w3schools.com/cssref/css3_pr_transition-timing-function.asp)

##Interaction

Property mixin						| Default value						| Description
--- | --- | ---
`.resize`							| `none`							| [Resize at W3Schools](http://www.w3schools.com/cssref/css3_pr_resize.asp)
`.appearance`						| `normal`							| [Appearance at W3Schools](http://www.w3schools.com/cssref/css3_pr_appearance.asp)
`.user-select`						| `auto`							| [User select at CSS-Tricks](http://css-tricks.com/almanac/properties/u/user-select/)

##Image

Property mixin						| Default value						| Description
--- | --- | ---
`.image-resolution`					| `1dppx`							| [Image resolution at CSS Portal](http://www.cssportal.com/css-properties/image-resolution.php)

##Background image

Property mixin						| Default value								| Description
--- | --- | ---
`.linear-gradient`					| `@gradient:top, #FFFFFF, #000000;`		| [Gradients at W3Schools](http://www.w3schools.com/css/css3_gradients.asp)
`.background-origin`				| `padding-box`								| [Background origin at W3Schools](http://www.w3schools.com/cssref/css3_pr_background-origin.asp)
`.background-clip`					| `border-box`								| [Background clip at W3Schools](http://www.w3schools.com/cssref/css3_pr_background-clip.asp)

##Simple transform

Property mixin				| Default value			| Description
--- | --- | ---
`.opacity`					| `1`					| [opacity at W3Schools](http://www.w3schools.com/css/css_image_transparency.asp)

##Print

Property mixin				| Default value					| Description
--- | --- | ---
`.marks`					| `none`						| [Marks at CSS3.com](http://www.css3.com/css-marks/)