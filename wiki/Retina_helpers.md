#Retina helpers

The contents of this page are located in `core/retina.less`.

##Background images

Below, a list of mixins useful to manage retina background images and optimize your page requests to make everything faster, based on the screen resolution and density.

###Background images mixins

- [.backgroundRetina](#backgroundretina)
- [.backgroundRetinaHdFull](#backgroundretinahdfull)
- [.backgroundRetinaHdReady](#backgroundretinahdready)
- [.backgroundRetinaTabletLandscape](#backgroundretinatabletlandscape)
- [.backgroundRetinaTabletPortrait](#backgroundretinatabletportrait)
- [.backgroundRetinaSmartphoneLandscape](#backgroundretinasmartphonelandscape)
- [.backgroundRetinaSmartphonePortrait](#backgroundretinasmartphoneportrait)
- [.backgroundRetinaResponsive](#backgroundretinaresponsive)

###Icons mixins

- [.backgroundRetinaIcon](#backgroundretinaicon)
- [.iconRetina](#iconretina)
- [.spriteRetina](#spriteretina)


##Background images mixins


##.backgroundRetina

It displays e default density image on standard displays and a retina image on retina displays

Parameter value					| Default value					| Description
--- | --- | ---
`@defaultImage`					| None							| A standard resolution image
`@retinaImage`					| `@defaultImage`				| A retina resolution image, it shoud be **2x larger** than the `@defaultImage`
`@backgroundSize`				| `auto`						| Sets the `background-size` CSS property

**LESS usage example**

```less
.css-selector {
	@backgroundSize1x: 150px 75px;
	.backgroundRetina(
		"image-background-1x.png",
		"image-background-2x.png",
		@backgroundSize1x
	);
}
```

Remember to set the `@backgroundSize` property with the 1x image sizes, this is important to ensure the mixin works correctly.

**CSS Result**

```css
.css-selector {
	/* Standard display */
	background-image:url("/css/frontsize/theme-name/img/image-background-1x.png");
	background-size:150px 75px;
}
@media only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Retina display */
		background-image:url("/css/frontsize/theme-name/img/image-background-2x.png");
	}
}
```

##.backgroundRetinaHdFull

Sets a background image from **Full HD viewport** with **Retina support**.

Parameter value				| Default value													| Description
--- | --- | ---
`@defaultHdFullImage`		| None															| A standard resolution image
`@retinaHdFullImage`		| `@defaultHdFullImage`											| A retina resolution image, it shoud be **2x larger** than the `@defaultHdFullImage`
`@rootPath`					| `''` or `@rootpath` (if `@use-rootpath` is set to `true`)		| Can override the `@rootpath` if `@use-rootpath` is set to `true`

**LESS usage example**

```less
/* in app.less file */
@use-rootpath: true;
@rootpath: '/css/frontsize/@{theme}/img/';

/* in your view_name.less file */

.css-selector {
	.backgroundRetinaHdFull(
		"image-background-1x.png",
		"image-background-2x.png"
	);
}
```

If you set `@use-rootpath` to `true` and define your theme path with `@rootpath` every `.backgroundRetina...` mixin will automatically add the `@rootpath` var value before the image **URL**.

**CSS Result**

```css
@media only screen and (min-width: 1800px) {
	.css-selector {
		/* Full HD */
		background-image:url("/css/frontsize/theme-name/img/image-background-1x.png");
	}
}
@media only screen and (min-width: 1800px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Full HD Retina */
		background-image:url("/css/frontsize/theme-name/img/image-background-2x.png");
	}
}
```

##.backgroundRetinaHdReady

Sets a background image from **HD Ready viewport** with **Retina support**.

Parameter value					| Default value												| Description
--- | --- | ---
`@defaultHdReadyRetinaImage`	| None														| A standard resolution image
`@retinaHdReadyRetinaImage`		| `@defaultHdReadyRetinaImage`								| A retina resolution image, it shoud be **2x larger** than the `@defaultHdReadyRetinaImage`
`@rootPath`						| `''` or `@rootpath` (if `@use-rootpath` is set to `true`)	| Can override the `@rootpath` if `@use-rootpath` is set to `true`

**LESS usage example**

```less
/* in app.less file */
@use-rootpath: true;
@rootpath: '/css/frontsize/@{theme}/img/';

/* in your view_name.less file */

.css-selector {
	.backgroundRetinaHdReady(
		"image-background-1x.png",
		"image-background-2x.png",
		"http://an-external-cdn.com/images/"
	);
}
```

While you set `@use-rootpath` to `true` and define your theme path with `@rootpath` every `.backgroundRetina...` can override the path by setting the `@rootPath` var with a different **URL**.

**CSS Result**

```css
@media only screen and (min-width: 1280px) {
	.css-selector {
		/* HD Ready */
		background-image:url("http://an-external-cdn.com/images/image-background-1x.png");
	}
}
@media only screen and (min-width: 1280px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* HD Ready Retina */
		background-image:url("http://an-external-cdn.com/images/image-background-2x.png");
	}
}
```

##.backgroundRetinaTabletLandscape

Sets a background image from **Tablet Landscape viewport** with **Retina support**.

Parameter value						| Default value												| Description
--- | --- | ---
`@defaultTabletLandscapeBackground`	| None														| A standard resolution image
`@retinaTabletLandscapeBackground`	| `@defaultTabletLandscapeBackground`						| A retina resolution image, it shoud be **2x larger** than the `@defaultTabletLandscapeBackground`
`@rootPath`							| `''` or `@rootpath` (if `@use-rootpath` is set to `true`)	| Can override the `@rootpath` if `@use-rootpath` is set to `true`

**LESS usage example**

```less
/* in app.less file */
@use-rootpath: false;

/* in your view_name.less file */

.css-selector {
	.backgroundRetinaTabletLandscape(
		"image-background-1x.png",
		"image-background-2x.png"
	);
}
```

While you set `@use-rootpath` to `false` every `.backgroundRetina...` will call the **URL** you've set directly.

**CSS Result**

```css
@media only screen and (min-width: 1024px) {
	.css-selector {
		/* Tablet Landscape */
		background-image:url("image-background-1x.png");
	}
}
@media only screen and (min-width: 1024px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Tablet Landscape Retina */
		background-image:url("image-background-2x.png");
	}
}
```

##.backgroundRetinaTabletPortrait

Sets a background image from **Tablet Portrait viewport** with **Retina support**.

Parameter value					| Default value						| Description
--- | --- | ---
`@defaultTabletPortraitBackground`	| None														| A standard resolution image
`@retinaTabletPortraitBackground`	| `@defaultTabletPortraitBackground`							| A retina resolution image, it shoud be **2x larger** than the `@defaultTabletPortraitBackground`
`@rootPath`							| `''` or `@rootpath` (if `@use-rootpath` is set to `true`)	| Can override the `@rootpath` if `@use-rootpath` is set to `true`

**LESS usage example**

```less
/* in app.less file */
@use-rootpath: false;

/* in your view_name.less file */

.css-selector {
	.backgroundRetinaTabletPortrait(
		"image-background-1x.png",
		"image-background-2x.png",
		"http://an-external-cdn.com/images/"
	);
}
```

While you set `@use-rootpath` to `false` every `.backgroundRetina...` can override the path by setting the `@rootPath` var with a different **URL**.

**CSS Result**

```css
@media only screen and (min-width: 768px) {
	.css-selector {
		/* Tablet Portrait */
		background-image:url("http://an-external-cdn.com/images/image-background-1x.png");
	}
}
@media only screen and (min-width: 768px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Tablet Portrait Retina */
		background-image:url("http://an-external-cdn.com/images/image-background-2x.png");
	}
}
```

##.backgroundRetinaSmartphoneLandscape

Sets a background image from **Smartphone Landscape viewport** with **Retina support**.

Parameter value							| Default value													| Description
--- | --- | ---
`@defaultSmartphoneLandscapeBackground`	| None															| A standard resolution image
`@retinaSmartphoneLandscapeBackground`	| `@defaultSmartphoneLandscapeBackground`						| A retina resolution image, it shoud be **2x larger** than the `@defaultSmartphoneLandscapeBackground`
`@rootPath`								| `''` or `@rootpath` (if `@use-rootpath` is set to `true`)		| Can override the `@rootpath` if `@use-rootpath` is set to `true`

**LESS usage example**

```less
/* in app.less file */
@use-rootpath: true;
@rootpath: '/css/frontsize/@{theme}/img/';

/* in your view_name.less file */

.css-selector {
	.backgroundRetinaSmartphoneLandscape(
		"http://an-external-cdn.com/images/image-background-1x.png",
		"http://another-external-cdn.com/images/image-background-2x.png",
		""
	);
}
```

While you set `@use-rootpath` to `true` and define your theme path with `@rootpath` every `.backgroundRetina...` can reach differents external sources by override the path by setting the `@rootPath` var with an empty **URL**.

**CSS Result**

```css 
@media only screen and (min-width: 480px) {
	.css-selector {
		/* Smartphone Landscape */
		background-image:url("http://an-external-cdn.com/images/image-background-1x.png");
	}
}
@media only screen and (min-width: 480px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Smartphone Landscape Retina */
		background-image:url("http://another-external-cdn.com/images/image-background-2x.png");
	}
}
```

##.backgroundRetinaSmartphonePortrait

Sets a background image from **Smartphone Portrait viewport** with **Retina support**.

Parameter value					| Default value						| Description
--- | --- | ---
`@defaultSmartphonePortraitBackground`	| None															| A standard resolution image
`@retinaSmartphonePortraitBackground`	| `@defaultSmartphonePortraitBackground`						| A retina resolution image, it shoud be **2x larger** than the `@defaultSmartphonePortraitBackground`
`@rootPath`								| `''` or `@rootpath` (if `@use-rootpath` is set to `true`)		| Can override the `@rootpath` if `@use-rootpath` is set to `true`

**LESS usage example**

```less
/* in app.less file */
@use-rootpath: false;

/* in your view_name.less file */

.css-selector {
	.backgroundRetinaSmartphonePortrait(
		"http://an-external-cdn.com/images/image-background-1x.png",
		"http://another-external-cdn.com/images/image-background-2x.png"
	);
}
```

While you set `@use-rootpath` to `false` every `.backgroundRetina...` can reach differents external sources.

**CSS Result**

```css 
@media only screen and (min-width: 1px) {
	.css-selector {
		/* Smartphone Portrait */
		background-image:url("http://an-external-cdn.com/images/image-background-1x.png");
	}
}
@media only screen and (min-width: 1px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Smartphone Portrait Retina */
		background-image:url("http://another-external-cdn.com/images/image-background-2x.png");
	}
}
```

##.backgroundRetinaResponsive

Sets a different background image for every viewport with **Retina support**.

Parameter value								| Default value													| Description
--- | --- | ---
`@defaultHdFullBackground`					| None															| Standard resolution `background-image` *CSS property* for the **Full HD** *HTML element*
`@retinaHdFullBackground`					| `@defaultHdFullBackground`									| Retina resolution `background-image` *CSS property* for the **Full HD** *HTML element*
`@defaultHdReadyRetinaBackground`			| `@defaultHdFullBackground`									| Standard resolution `background-image` *CSS property* for the **HD Ready** *HTML element*
`@retinaHdReadyRetinaBackground`			| `@defaultHdReadyRetinaBackground`								| Retina resolution `background-image` *CSS property* for the **HD Ready** *HTML element*
`@defaultTabletLandscapeBackground`			| `@defaultHdReadyRetinaBackground`								| Standard resolution `background-image` *CSS property* for the **Tablet Landscape** *HTML element*
`@retinaTabletLandscapeBackground`			| `@defaultTabletLandscapeBackground`							| Retina resolution `background-image` *CSS property* for the **Tablet Landscape** *HTML element*
`@defaultTabletPortraitBackground`			| `@defaultTabletLandscapeBackground`							| Standard resolution `background-image` *CSS property* for the **Tablet Portrait** *HTML element*
`@retinaTabletPortraitBackground`			| `@defaultTabletPortraitBackground`							| Retina resolution `background-image` *CSS property* for the **Tablet Portrait** *HTML element*
`@defaultSmartphoneLandscapeBackground`		| `@defaultTabletPortraitBackground`							| Standard resolution `background-image` *CSS property* for the **Smartphone Landscape** *HTML element*
`@retinaSmartphoneLandscapeBackground`		| `@defaultSmartphoneLandscapeBackground`						| Retina resolution `background-image` *CSS property* for the **Smartphone Landscape** *HTML element*
`@defaultSmartphonePortraitBackground`		| `@defaultSmartphoneLandscapeBackground`						| Standard resolution `background-image` *CSS property* for the **Smartphone Portrait** *HTML element*
`@retinaSmartphonePortraitBackground`		| `@defaultSmartphonePortraitBackground`						| Retina resolution `background-image` *CSS property* for the **Smartphone Portrait** *HTML element*
`@backgroundSize`							| `auto`														| Sets `background-size` *CSS property* for all background images
`@rootPath`									| `''` or `@rootpath` (if `@use-rootpath` is set to `true`)		| Can override the `@rootpath` if `@use-rootpath` is set to `true`

**LESS usage example**

```less
.css-selector {
	.backgroundRetinaResponsive(
		"background-image-hd-full-1x.png",
		"background-image-hd-full-2x.png",
		"background-image-hd-ready-1x.png",
		"background-image-hd-ready-2x.png",
		"background-image-tablet-landscape-1x.png",
		"background-image-tablet-landscape-2x.png",
		"background-image-tablet-portrait-1x.png",
		"background-image-tablet-portrait-2x.png",
		"background-image-smartphone-landscape-1x.png",
		"background-image-smartphone-landscape-2x.png",
		"background-image-smartphone-portrait-1x.png",
		"background-image-smartphone-portrait-2x.png",
		contain
	);
}
```

Everything wrote for the previous mixins works for this one too.

**CSS Result**

```css
.css-selector {
	background-size:contain;
}
@media only screen and (min-width: 1px) {
	.css-selector {
		/* Smartphone Portrait */
		background-image:url("background-image-smartphone-portrait-1x.png");
	}
}
@media only screen and (min-width: 1px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Smartphone Portrait Retina */
		background-image:url("background-image-smartphone-portrait-2x.png");
	}
}
@media only screen and (min-width: 480px) {
	.css-selector {
		/* Smartphone Landscape */
		background-image:url("background-image-smartphone-landscape-1x.png");
	}
}
@media only screen and (min-width: 480px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Smartphone Landscape Retina */
		background-image:url("background-image-smartphone-landscape-2x.png");
	}
}
@media only screen and (min-width: 768px) {
	.css-selector {
		/* Tablet Portrait */
		background-image:url("background-image-tablet-portrait-1x.png");
	}
}
@media only screen and (min-width: 768px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Tablet Portrait Retina */
		background-image:url("background-image-tablet-portrait-2x.png");
	}
}
@media only screen and (min-width: 1024px) {
	.css-selector {
		/* Tablet Landscape */
		background-image:url("background-image-tablet-landscape-1x.png");
	}
}
@media only screen and (min-width: 1024px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Tablet Landscape Retina */
		background-image:url("background-image-tablet-landscape-2x.png");
	}
}
@media only screen and (min-width: 1280px) {
	.css-selector {
		/* HD Ready */
		background-image:url("background-image-hd-ready-1x.png");
	}
}
@media only screen and (min-width: 1280px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* HD Ready Retina */
		background-image:url("background-image-hd-ready-2x.png");
	}
}
@media only screen and (min-width: 1800px) {
	.css-selector {
		/* Full HD */
		background-image:url("background-image-hd-full-1x.png");
	}
}
@media only screen and (min-width: 1800px), only screen and (min-device-pixel-ratio: 2) {
	.css-selector {
		/* Full HD Retina */
		background-image:url("background-image-hd-full-2x.png");
	}
}
```

##Icons mixins


##.backgroundRetinaIcon

Sets an image inside an *HTML element*, can be useful to create background images with retina displays support.

Paramter value			| Default value					| Description
--- | --- | ---
`@defaultImage`			| None							| Standard resolution `background-image` *CSS property* for the *HTML element*
`@retinaImage`			| `@defaultImage`				| Retina resolution `background-image` *CSS property* for the *HTML element*
`@width`				| `100%`						| Sets the `width` *CSS property* for the *HTML element* 
`@height`				| `@width`						| Sets the `height` *CSS property* for the *HTML element* 

**LESS usage example**

```less
.css-selector {
	.backgroundRetinaIcon("icon-1x.png", "icon-2x.png", 24px);
}
```

**CSS Result**

```css
.css-selector {
	background-size:24px 24px;
	background-repeat: no-repeat;
	background-image:url("icon-1x.png");
}
@media only screen and (-webkit-min-device-pixel-ratio: 2) and (aspect-ratio: 2),
	only screen and (-webkit-min-device-pixel-ratio: 2),
	only screen and (min--moz-device-pixel-ratio: 2),
	only screen and (-o-min-device-pixel-ratio: 2/1),
	only screen and (min-device-pixel-ratio: 2),
	only screen and (min-resolution: 2dppx) {
		.css-selector {
			background-image:url("icon-2x.png");
		}
}
```

##.iconRetina

Sets an image inside an *HTML element* with a specific size, can be useful to create icons with retina displays support.

Paramter value			| Default value					| Description
--- | --- | ---
`@defaultImage`			| None							| Standard resolution `background-image` *CSS property* for the *HTML element*
`@retinaImage`			| None							| Retina resolution `background-image` *CSS property* for the *HTML element*
`@width`				| None							| Sets the `width` *CSS property* for the *HTML element* 
`@height`				| `@width`						| Sets the `height` *CSS property* for the *HTML element* 


**LESS usage example**

```less
.css-selector {
	.iconRetina("icon-1x.png", "icon-2x.png", 24px);
}
```

**CSS Result**

```css
.css-selector {
	width: 24px;
	height: 24px;
	background-size:24px 24px;
	background-repeat: no-repeat;
	background-image:url("icon-1x.png");
}
@media only screen and (-webkit-min-device-pixel-ratio: 2) and (aspect-ratio:2),
	only screen and (-webkit-min-device-pixel-ratio: 2),
	only screen and (min--moz-device-pixel-ratio: 2),
	only screen and (-o-min-device-pixel-ratio: 2/1),
	only screen and (min-device-pixel-ratio: 2),
	only screen and (min-resolution: 2dppx) {
		.css-selector {
			background-image:url("icon-2x.png");
		}
}
```

##.spriteRetina

Sets a background image as sprite for an *HTML element* with supports **Retina resolution**.

Paramter value				| Default value						| Description
--- | --- | ---
`@defaultImage`				| 									| Standard resolution `background-image` *CSS property* for the *HTML element*
`@retinaImage`				| 									| Retina resolution `background-image` *CSS property* for the *HTML element*
`@width`					| 									| Sets the `width` *CSS property* for the *HTML element* 
`@height`					| 									| Sets the `height` *CSS property* for the *HTML element* 
`@imageWidth`				| 									| Sets the `width` for the `background-size` *CSS property* for the *HTML element* when in **Retina resolution**
`@imageHeight`				| `value`							| Sets the `height` for the `background-size` *CSS property* for the *HTML element* when in **Retina resolution**

In the example below, we'll try to work with a styled checkbox with this sprite:

![Checkbox sprite](http://imagizer.imageshack.us/v2/64x32q90/62/vs37.png "Checkbox sprite")

The sprite will be a `32px` width and `16px` height image, every sprite state will be `16px` x `16px` icon.

**LESS usage example**

```less
.css-selector {
	@stepSize: 16px;
	@imageWidth: 32px; /* The sprite has two images placed horizontally */
	@imageHeight: 16px;
	
	.spriteRetina(
		"sprite-checkbox-1x.png",
		"sprite-checkbox-2x.png",
		@stepSize,
		@stepSize,
		@imageWidth,
		@imageHeight
	);
	.spritePosition(0, 0, @stepSize);

	&.checked {
		/* CSS state */
		.spritePosition(1, 0, @stepSize);
	}
}
```

**CSS Result**

```css
.css-selector {
	background-image:url("sprite-checkbox-1x.png");
	background-repeat:no-repeat;
	background-size:auto;
	box-sizing: border-box;
	-webkit-box-sizing: border-box;
	-khtml-box-sizing: border-box;
	-moz-box-sizing: border-box;
	-ms-box-sizing: border-box;
	-o-box-sizing: border-box;
	width:16px;
	height:16px;
}
@media only screen and (-webkit-min-device-pixel-ratio: 2) and (aspect-ratio:2),
	only screen and (-webkit-min-device-pixel-ratio: 2),
	only screen and (min--moz-device-pixel-ratio: 2),
	only screen and (-o-min-device-pixel-ratio: 2/1),
	only screen and (min-device-pixel-ratio: 2),
	only screen and (min-resolution: 2dppx) {
		.css-selector {
			background-size:16px 32px;
			background-image:url("sprite-checkbox-2x.png");
		}
}
```