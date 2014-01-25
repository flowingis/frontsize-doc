#Media queries

Helpers are used in the **LESS** files inside your theme, these mixins can be useful to build a consistent layouts where everything is easy to be edited and fast to be created.

The contents of this page are located in `core/media_queries.less` and `core/retina.less`.

###Page index

- [From a viewport](#from-a-viewport)
- [To a viewport](#to-a-viewport)
- [From a viewport To a viewport](#from-a-viewport-to-a-viewport)
- [Retina viewport](#retina-viewport)
- [Pixel density rules](#pixel-density-rules)
- [State](#state)
	- [Text](#text)
	- [Sizing](#sizing)
	- [Displaying](#displaying)
	- [Positioning](#positioning)
	- [Retina](#retina)
- [Helper](#helper)
	- [Background images](#background-images)

##From a viewport

Media queries for selectors active from a specific resolution or higher

Viewport rule					| Description
--- | ---
`@from-smartphone-portrait`		| Basically useless, it's active from **Smartphone portrait** to higher viewports
`@from-smartphone-landscape`	| Active from **Smartphone landscape** to higher viewports
`@from-tablet-portrait`			| Active from **Tablet portrait** to higher viewports
`@from-tablet-landscape`		| Active from **Tablet landscape** to higher viewports
`@from-hd-ready`				| Active from **HD Ready** to higher viewports
`@from-hd-full`					| Active from **Full HD** viewport

Every of these media queries viewport rules can used inside Frontsize like this:

**LESS usage example**

```less
@media @from-hd-ready {
	.selector-name {
		background-color: blue;
	}
}
```

**CSS result**

```css
@media only screen and (min-width: 1280px) {
	.selector-name {
		background-color: blue;
	}
}
```

##To a viewport
Media queries for selectors active from the smaller resolution to a specific one

Viewport rule					| Description
--- | ---
`@till-smartphone-portrait`		| Basically useless, it's active untill **Smartphone portrait** viewport, which is excluded from the rule
`@till-smartphone-landscape`	| Active untill **Smartphone landscape** viewport, which is excluded from the rule
`@till-tablet-portrait`			| Active untill **Tablet portrait** viewport, which is excluded from the rule
`@till-tablet-landscape`		| Active untill **Tablet landscape** viewport, which is excluded from the rule
`@till-hd-ready`				| Active untill **HD Ready** viewport, which is excluded from the rule
`@till-hd-full`					| Active untill **Full HD** viewport, which is excluded from the rule

Every of these media queries viewport rules can used inside Frontsize like this:

**LESS usage example**

```less
@media @till-hd-ready {
	.selector-name {
		background-color: blue;
	}
}
```

**CSS result**

```css
@media only screen and (max-width: 1279px) {
	.selector-name {
		background-color: blue;
	}
}
```

##From a viewport To a viewport

Media queries for strict resolution range selectors

Viewport rule					| Description
--- | ---
`@only-smartphone-portrait`		| Active only in **Smartphone portrait** viewport
`@only-smartphone-landscape`	| Active only in **Smartphone landscape** viewport
`@only-tablet-portrait`			| Active only in **Tablet portrait** viewport
`@only-tablet-landscape`		| Active only in **Tablet landscape** viewport
`@only-hd-ready`				| Active only in **HD Ready** viewport
`@only-hd-full`					| Active only in **Full HD** viewport

Every of these media queries viewport rules can used inside Frontsize like this:

**LESS usage example**

```less
@media @only-hd-ready {
	.selector-name {
		background-color: blue;
	}
}
```

**CSS result**

```css
@media only screen and (min-width: 1280px) and (max-width: 1799px) {
	.selector-name {
		background-color: blue;
	}
}
```

##Retina viewport

Viewport rule							| Description
--- | ---
`@retina-from-smartphone-portrait`		| Basically useless, it's active from **Smartphone portrait** to higher viewports if pixel ratio is 2
`@retina-from-smartphone-landscape`		| Active from **Smartphone landscape** to higher viewports if pixel ratio is 2
`@retina-from-tablet-portrait`			| Active from **Tablet portrait** to higher viewports if pixel ratio is 2
`@retina-from-tablet-landscape`			| Active from **Tablet landscape** to higher viewports if pixel ratio is 2
`@retina-from-hd-ready`					| Active from **HD Ready** to higher viewports if pixel ratio is 2
`@retina-from-hd-full`					| Active from **Full HD** viewport if pixel ratio is 2

Every of these media queries viewport rules can used inside Frontsize like this:

**LESS usage example**

```less
@media @retina-from-hd-ready {
	.selector-name {
		background-color: blue;
	}
}
```

**CSS result**

```css
@media only screen and (min-width: 1280px), only screen and (min-device-pixel-ratio: 2) {
	.selector-name {
		background-color: blue;
	}
}
```

##Pixel density rules

Viewport rule			| Description
--- | ---
`@display-retina`						| Active from **every** viewport if pixel ratio is 2, not recommended
`@display-retina-browser-compatible`	| Active from **every** viewport if pixel ratio is 2, recommended
`@display-standard`						| Active from **every** viewport if pixel ratio is not 2

Every of these media queries viewport rules can used inside Frontsize like this:

**LESS usage example**

```less
@media @display-retina {
	.selector-name {
		background-color: blue;
	}
}
```

**CSS result**

```css
@media	only screen and (-webkit-min-device-pixel-ratio: 2) and (aspect-ratio: 2)
		only screen and (-webkit-min-device-pixel-ratio: 2),
		only screen and (min--moz-device-pixel-ratio: 2),
		only screen and (-o-min-device-pixel-ratio: 2/1),
		only screen and (min-device-pixel-ratio: 2),
		only screen and (min-resolution: 2dppx) {
	.selector-name {
		background-color: blue;
	}
}
```


##State

The contents of this page are located in `core/state.less`.

##Text

Selector name								| Description
--- | ---
`.text-left-from-hd-full`					| Sets `text-align` *CSS* property to `left` from **Full HD** viewport
`.text-left-from-hd-ready`					| Sets `text-align` *CSS* property to `left` from **HD Ready** viewport
`.text-left-from-tablet-landscape`			| Sets `text-align` *CSS* property to `left` from **Tablet landscape** viewport
`.text-left-from-tablet-portrait`			| Sets `text-align` *CSS* property to `left` from **Tablet portrait** viewport
`.text-left-from-smartphone-landscape`		| Sets `text-align` *CSS* property to `left` from **Smartphone landscape** viewport
`.text-left-from-smartphone-portrait`		| Sets `text-align` *CSS* property to `left` from **Smartphone portrait** viewport
`.text-left-till-hd-full`					| Sets `text-align` *CSS* property to `left` until **Full HD** viewport excluded
`.text-left-till-hd-ready`					| Sets `text-align` *CSS* property to `left` until **HD Ready** viewport excluded
`.text-left-till-tablet-landscape`			| Sets `text-align` *CSS* property to `left` until **Tablet landscape** viewport excluded
`.text-left-till-tablet-portrait`			| Sets `text-align` *CSS* property to `left` until **Tablet portrait** viewport excluded
`.text-left-till-smartphone-landscape`		| Sets `text-align` *CSS* property to `left` until **Smartphone landscape** viewport excluded
`.text-centered-from-hd-full`				| Sets `text-align` *CSS* property to `center` from **Full HD** viewport
`.text-centered-from-hd-ready`				| Sets `text-align` *CSS* property to `center` from **HD Ready** viewport
`.text-centered-from-tablet-landscape`		| Sets `text-align` *CSS* property to `center` from **Tablet landscape** viewport
`.text-centered-from-tablet-portrait`		| Sets `text-align` *CSS* property to `center` from **Tablet portrait** viewport
`.text-centered-from-smartphone-landscape`	| Sets `text-align` *CSS* property to `center` from **Smartphone landscape** viewport
`.text-centered-from-smartphone-portrait`	| Sets `text-align` *CSS* property to `center` from **Smartphone portrait** viewport
`.text-centered-till-hd-full`				| Sets `text-align` *CSS* property to `center` until **Full HD** viewport excluded
`.text-centered-till-hd-ready`				| Sets `text-align` *CSS* property to `center` until **HD Ready** viewport excluded
`.text-centered-till-tablet-landscape`		| Sets `text-align` *CSS* property to `center` until **Tablet landscape** viewport excluded
`.text-centered-till-tablet-portrait`		| Sets `text-align` *CSS* property to `center` until **Tablet portrait** viewport excluded
`.text-centered-till-smartphone-landscape`	| Sets `text-align` *CSS* property to `center` until **Smartphone landscape** viewport excluded
`.text-right-from-hd-full`					| Sets `text-align` *CSS* property to `right` from **Full HD** viewport
`.text-right-from-hd-ready`					| Sets `text-align` *CSS* property to `right` from **HD Ready** viewport
`.text-right-from-tablet-landscape`			| Sets `text-align` *CSS* property to `right` from **Tablet landscape** viewport
`.text-right-from-tablet-portrait`			| Sets `text-align` *CSS* property to `right` from **Tablet portrait** viewport
`.text-right-from-smartphone-landscape`		| Sets `text-align` *CSS* property to `right` from **Smartphone landscape** viewport
`.text-right-from-smartphone-portrait`		| Sets `text-align` *CSS* property to `right` from **Smartphone portrait** viewport
`.text-right-till-hd-full`					| Sets `text-align` *CSS* property to `right` until **Full HD** viewport excluded
`.text-right-till-hd-ready`					| Sets `text-align` *CSS* property to `right` until **HD Ready** viewport excluded
`.text-right-till-tablet-landscape`			| Sets `text-align` *CSS* property to `right` until **Tablet landscape** viewport excluded
`.text-right-till-tablet-portrait`			| Sets `text-align` *CSS* property to `right` until **Tablet portrait** viewport excluded
`.text-right-till-smartphone-landscape`		| Sets `text-align` *CSS* property to `right` until **Smartphone landscape** viewport excluded


##Sizing

Selector name						| Description
--- | ---
`.fill-till-hd-full`					| Sets the `width` *CSS* property to `100%` until **Full HD** viewport excluded
`.almost-till-hd-full`					| Sets the `width` *CSS* property to `75%` until **Full HD** viewport excluded
`.half-till-hd-full`					| Sets the `width` *CSS* property to `50%` until **Full HD** viewport excluded
`.little-till-hd-full`					| Sets the `width` *CSS* property to `25%` until **Full HD** viewport excluded
`.fill-till-hd-ready`					| Sets the `width` *CSS* property to `100%` until **HD Ready** viewport excluded
`.almost-till-hd-ready`					| Sets the `width` *CSS* property to `75%` until **HD Ready** viewport excluded
`.half-till-hd-ready`					| Sets the `width` *CSS* property to `50%` until **HD Ready** viewport excluded
`.little-till-hd-ready`					| Sets the `width` *CSS* property to `25%` until **HD Ready** viewport excluded
`.fill-till-tablet-landscape`			| Sets the `width` *CSS* property to `100%` until **Tablet landscape** viewport excluded
`.almost-till-tablet-landscape`			| Sets the `width` *CSS* property to `75%` until **Tablet landscape** viewport excluded
`.half-till-tablet-landscape`			| Sets the `width` *CSS* property to `50%` until **Tablet landscape** viewport excluded
`.little-till-tablet-landscape`			| Sets the `width` *CSS* property to `25%` until **Tablet landscape** viewport excluded
`.fill-till-tablet-portrait`			| Sets the `width` *CSS* property to `100%` until **Tablet portrait** viewport excluded
`.almost-till-tablet-portrait`			| Sets the `width` *CSS* property to `75%` until **Tablet portrait** viewport excluded
`.half-till-tablet-portrait`			| Sets the `width` *CSS* property to `50%` until **Tablet portrait** viewport excluded
`.little-till-tablet-portrait`			| Sets the `width` *CSS* property to `25%` until **Tablet portrait** viewport excluded
`.fill-till-smartphone-landscape`		| Sets the `width` *CSS* property to `100%` until **Smartphone landscape** viewport excluded
`.almost-till-smartphone-landscape`		| Sets the `width` *CSS* property to `75%` until **Smartphone landscape** viewport excluded
`.half-till-smartphone-landscape`		| Sets the `width` *CSS* property to `50%` until **Smartphone landscape** viewport excluded
`.little-till-smartphone-landscape`		| Sets the `width` *CSS* property to `25%` until **Smartphone landscape** viewport excluded


##Visibility

Selector name						| Description
--- | ---
`.block-till-hd-full`				| Sets the `display` *CSS* property to `block` until **Full HD** viewport excluded
`.block-till-hd-ready`				| Sets the `display` *CSS* property to `block` until **HD Ready** viewport excluded
`.block-till-tablet-landscape`		| Sets the `display` *CSS* property to `block` until **Tablet landscape** viewport excluded
`.block-till-tablet-portrait`		| Sets the `display` *CSS* property to `block` until **Tablet portrait** viewport excluded
`.block-till-smartphone-landscape`	| Sets the `display` *CSS* property to `block` until **Smartphone landscape** viewport excluded
`.not-from-hd-full`					| Sets the `display` *CSS* property to `none` from **Full HD** viewport
`.not-from-hd-ready`				| Sets the `display` *CSS* property to `none` from **HD Ready** viewport
`.not-from-tablet-landscape`		| Sets the `display` *CSS* property to `none` from **Tablet landscape** viewport
`.not-from-tablet-portrait`			| Sets the `display` *CSS* property to `none` from **Tablet portrait** viewport
`.not-from-smartphone-landscape`	| Sets the `display` *CSS* property to `none` from **Smartphone landscape** viewport
`.not-from-smartphone-portrait`		| Sets the `display` *CSS* property to `none` from **Smartphone portrait** viewport
`.not-till-hd-full`					| Sets the `display` *CSS* property to `none` until **Full HD** viewport excluded
`.not-till-hd-ready`				| Sets the `display` *CSS* property to `none` until **HD Ready** viewport excluded
`.not-till-tablet-landscape`		| Sets the `display` *CSS* property to `none` until **Tablet landscape** viewport excluded
`.not-till-tablet-portrait`			| Sets the `display` *CSS* property to `none` until **Tablet portrait** viewport excluded
`.not-till-smartphone-landscape`	| Sets the `display` *CSS* property to `none` until **Smartphone landscape** viewport excluded
`.not-on-hd`						| Sets the `display` *CSS* property to `none` on **Full HD** and **HD Ready** viewports
`.not-on-hd-full`					| Sets the `display` *CSS* property to `none` on **Full HD** viewport
`.not-on-hd-ready`					| Sets the `display` *CSS* property to `none` on **HD Ready** viewport
`.not-on-tablet`					| Sets the `display` *CSS* property to `none` on **Tablet landscape** and **Tablet portrait** viewports
`.not-on-tablet-landscape`			| Sets the `display` *CSS* property to `none` on **Tablet landscape** viewport
`.not-on-tablet-portrait`			| Sets the `display` *CSS* property to `none` on **Tablet portrait** viewport
`.not-on-smartphone`				| Sets the `display` *CSS* property to `none` on **Smartphone landscape** and **Smartphone portrait** viewports
`.not-on-smartphone-landscape`		| Sets the `display` *CSS* property to `none` on **Smartphone landscape** viewport
`.not-on-smartphone-portrait`		| Sets the `display` *CSS* property to `none` on **Smartphone portrait** viewport
`.only-on-hd`						| The element is visible on **Full HD** and **HD Ready** viewports
`.only-on-hd-full`					| The element is visible on **Full HD** viewport
`.only-on-hd-ready`					| The element is visible on **HD Ready** viewport
`.only-on-tablet`					| The element is visible on **Tablet landscape** and **Tablet portrait** viewports
`.only-on-tablet-landscape`			| The element is visible on **Tablet landscape** viewport
`.only-on-tablet-portrait`			| The element is visible on **Tablet portrait** viewport
`.only-on-smartphone`				| The element is visible on **Smartphone landscape** and **Smartphone portrait** viewports
`.only-on-smartphone-landscape`		| The element is visible on **Smartphone landscape** viewport
`.only-on-smartphone-portrait`		| The element is visible on **Smartphone portrait** viewport


##Positioning

Selector name						| Description
--- | ---
`.not-hooked-till-tablet-landscape`		| Sets the `position` *CSS* property to `static` until **Tablet landscape** viewport excluded
`.not-hooked-till-tablet-portrait`		| Sets the `position` *CSS* property to `static` until **Tablet portrait** viewport excluded
`.to-center-till-hd-full`				| margin: auto
`.to-left-till-hd-full`					| float: left
`.to-right-till-hd-full`				| float: right
`.to-center-till-hd-ready`				| margin: auto
`.to-left-till-hd-ready`				| float: left
`.to-right-till-hd-ready`				| float: right
`.to-center-till-tablet-landscape`		| margin: auto
`.to-left-till-tablet-landscape`		| float: left
`.to-right-till-tablet-landscape`		| float: right
`.to-center-till-tablet-portrait`		| margin: auto
`.to-left-till-tablet-portrait`			| float: left
`.to-right-till-tablet-portrait`		| float: right
`.to-center-till-smartphone-landscape`	| margin: auto
`.to-left-till-smartphone-landscape`	| float: left
`.to-right-till-smartphone-landscape`	| float: right
`.to-center-from-smartphone-portrait`	| margin: auto
`.to-left-from-smartphone-portrait`		| float: left
`.to-right-from-smartphone-portrait`	| float: right
`.to-center-from-smartphone-landscape`	| margin: auto
`.to-left-from-smartphone-landscape`	| float: left
`.to-right-from-smartphone-landscape`	| float: right
`.to-center-from-tablet-portrait`		| margin: auto
`.to-left-from-tablet-portrait`			| float: left
`.to-right-from-tablet-portrait`		| float: right
`.to-center-from-tablet-landscape`		| margin: auto
`.to-left-from-tablet-landscape`		| float: left
`.to-right-from-tablet-landscape`		| float: right
`.to-center-from-hd-ready`				| margin: auto
`.to-left-from-hd-ready`				| float: left
`.to-right-from-hd-ready`				| float: right
`.to-center-from-hd-full`				| margin: auto
`.to-left-from-hd-full`					| float: left
`.to-right-from-hd-full`				| float: right


##Retina

Selector name		| Description
--- | ---
`.not-retina-only`	| Sets the `display` *CSS* property to `none` if the screen resolution supports `1dppx` density
`.retina-only`		| Sets the `display` *CSS* property to `none` if the screen resolution supports `2dppx` density

##Helpers

The contents of this page are located in `core/helpers.less`.

#Background images

These responsive rules works with standard resulution only, if you need to work with retina images too see the [Retina helper](https://github.com/vitto/frontsize-less/wiki/Retina_helpers/#background-images) section page.

##.backgroundResponsive

It sets a different background image for every viewport.

**LESS usage example**

```less
/* in app.less file */
@use-rootpath: false;

/* in your view_name.less file */

.css-selector {
	.backgroundResponsive(
		"background-image-hd-full.png",
		"background-image-hd-ready.png",
		"background-image-tablet-landscape.png",
		"background-image-tablet-portrait.png",
		"background-image-smartphone-landscape.png",
		"background-image-smartphone-portrait.png"
	);
}
```

While you set `@use-rootpath` to `false` the mixin `.backgroundResponsive` will call the **URL** you've set directly.

**CSS Result**

```css
@media only screen and (min-width: 1800px) {
	.css-selector {
		background-image:url("background-image-hd-full.png");
	}
}
@media only screen and (min-width: 1280px) {
	.css-selector {
		background-image:url("background-image-hd-ready.png");
	}
}
@media only screen and (min-width: 1024px) {
	.css-selector {
		background-image:url("background-image-tablet-landscape.png");
	}
}
@media only screen and (min-width: 768px) {
	.css-selector {
		background-image:url("background-image-tablet-portrait.png");
	}
}
@media only screen and (min-width: 480px) {
	.css-selector {
		background-image:url("background-image-smartphone-landscape.png");
	}
}
@media only screen and (min-width: 1px) {
	.css-selector {
		background-image:url("background-image-smartphone-portrait.png");
	}
}
```

##.backgroundHdFull

Sets the **URL** for the `background-image` *CSS* property for **Full HD** viewport.

**LESS usage example**

```less
/* in app.less file */
@use-rootpath: false;

/* in your view_name.less file */

.css-selector {
	.backgroundHdFull(
		"background-image-hd-full.png"
	);
}
```

While you set `@use-rootpath` to `false` the mixin `.backgroundResponsive` will call the **URL** you've set directly.

**CSS Result**

```css
@media only screen and (min-width: 1800px) {
	.css-selector {
		background-image:url("background-image-hd-full.png");
	}
}
```

Selector name						| Description
--- | ---
`.backgroundHdFull`					| Sets the **URL** for the `background-image` *CSS* property for **Full HD** viewport.
`.backgroundHdReady`				| Sets the **URL** for the `background-image` *CSS* property for **HD Ready** viewport.
`.backgroundTabletLandscape`		| Sets the **URL** for the `background-image` *CSS* property for **Tablet Landscape** viewport.
`.backgroundTabletPortrait`			| Sets the **URL** for the `background-image` *CSS* property for **Tablet Portrait** viewport.
`.backgroundSmartphoneLandscape`	| Sets the **URL** for the `background-image` *CSS* property for **Smartphone Landscape** viewport.
`.backgroundSmartphonePortrait`		| Sets the **URL** for the `background-image` *CSS* property for **Smartphone Portrait** viewport.