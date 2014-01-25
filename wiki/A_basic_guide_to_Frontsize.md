#A basic guide to Frontsize

This is an introduction to what you get and what you can do with **Frontsize**

###Page index

- [Features](#features)
	- [Built to build](#built-to-build)
	- [TV Compatible](#tv-compatible)
	- [Fully configurable](#fully-configurable)
	- [Retina support for images](#retina-support-for-images)
	- [Scalable fonts](#scalable-fonts)
	- [Widget components](#widget-components)
	- [Helper mixins](#helper-mixins)
	- [Modular state selectors](#modular-state-selectors)
- [App configuration](#app-configuration)
- [Grids](#grids)
	- How to work with grids
	- Mixin (addViewportsSteps)
	- Multiple rows container
	- Single row container
	- Spacing columns
- Theme
	- Base
	- Dependances
	- Organize theme images
	- Layout elements
	- Vars
	- Views
	- Theme widgets
	- Theme helpers
- Migration
	- From Bootstrap to Frontsize
	- From Foundation to Frontsize
- Best practice
	- Style the widgets, not the grid
	- Create state selectors instead of static CSS



#Features

This page is written to help people choose if this can be helpful for their needs.

---

###Built to build

Frontsize was created for front-end developers who need a solid environment to create complex themes for their projects.

The framework is focused on *mixins*, *vars* and *CSS state selectors* dedicated to theming with the [SMACSS][9] approach and to be responsive and readable on every viewport, from mobile to HD.

---

###TV Compatible

By using the mixin `.setFontScaling` it's possible to set a different global `font-size` for every viewport, this is particulary useful for high screen resolutions like Full HD viewd from 3m of distance and keep the readable.
A website viewed on the **Home HD TVs** displays too small fonts to be viewed from 3m of distance, Frontsize gives you the possibility to view websites also from your tv without loos your eyes on small fonts.


**LESS usage example**

Let's see how your `app.less` can be configured with a basic configuration:

```
@font-size: 1em;
@font-line-height: 1.25;

.setFontScaling();
```

You can also set the font sizes manually like in the next example:

```
@hdFull: 1.5em;
@hdReady: 1.25em;
@tabletLandscape: 1em;
@tabletPortrait: 1em;
@smartphoneLandscape: 1em;
@smartphonePortrait: 0.875em;
@fontLineHeight: 1.25;

.setFontScaling(@hdFull, @hdReady, @tabletLandscape, @tabletPortrait, @smartphoneLandscape, @smartphonePortrait, @fontLineHeight);
```

For more examples go to the [Fonts](https://github.com/vitto/frontsize-less/wiki/Fonts/#setFontScaling) page.

#####TV dedicated viewports

If your web project is expected to work especially on TVs, this is the framework for you, there are media queries rules just for **HD Ready** and **Full HD** viewports like:

HD Ready rule					| Description
-|-
`@from-hd-ready`				| Active from **HD Ready** to higher viewports
`@till-hd-ready`				| Active untill **HD Ready** viewport, which is excluded from the rule
`@only-hd-ready`				| Active only in **HD Ready** viewport
`@retina-from-hd-ready`			| Active from **HD Ready** to higher viewports if pixel ratio is 2

Full HD rule					| Description
-|-
`@from-hd-full`					| Active from **Full HD** viewport
`@till-hd-full`					| Active untill **Full HD** viewport, which is excluded from the rule
`@only-hd-full`					| Active only in **Full HD** viewport
`@retina-from-hd-full`			| Active from **Full HD** viewport if pixel ratio is 2

To see the difference in details go to the [media queries](https://github.com/vitto/frontsize-less/wiki/Media_queries/#from-a-viewport) page.

###Fully configurable

Frontsize is built to create frontend environments and lets you decide what you want to use and what you won't.

####Set CSS3 browser prefixes when you want

You can set all CSS3 prefixes by calling their specific CSS3 mixins, like for [box-shadow](#box-shadow-example) mixin, then, you can change this settings when you want.

####Define your viewport media queries

You can configure all the 28 media query viewport rules of Frontsize by setting just 6 variables that will affect all the behavior of the framework consistently.

```less
@smartphone-portrait-step:	320px;	// smartphones portrait		320~380
@smartphone-landscape-step:	480px;	// smartphones landscape	480~568~685
@tablet-portrait-step:		768px;	// tablet portrait			768
@tablet-landscape-step:		1024px;	// tablet landscape			1024
@hd-ready-step:				1280px;	// HD Ready					1280 (720p)
@hd-full-step:				1800px;	// Full HD					1920 (1080p)

```

These variable will affects the media queries rules listed on [media queries](https://github.com/vitto/frontsize-less/wiki/Media_queries/#from-a-viewport) page.

###Retina support for images

It's possible to work with standard and retina images with just some rows of code and let the framework do the job for you:

**Responsive background image**

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

For more information, visit [Retina helpers](https://github.com/vitto/frontsize-less/wiki/Retina_helpers/#backgroundretina) section.

###Scalable fonts

It's possible to set global rules to the font's sizing behavior of your website application, that's nice if you plan to build something that should be visible from a **Smartphone** to a **Full HD TV**.

For more information, visit [Fonts](https://github.com/vitto/frontsize-less/wiki/Fonts/) section.

###Widget components

There is a community behind **Frontsize** dedicated to [widgets components][8], you can write your own, make it public or private.

These widgets are useful for creating stand-alone CSS components reusable everywhere around your website without breaking your layout.

###Helper mixins components

Use the [Helper mixins](https://github.com/vitto/frontsize-less/wiki/Helpers/) to make your styles environment more solid and write less code:

**LESS example of Helpers**

```less
.selector {
	.size(32px);
	.roundBottom(8px);
	.verticalGradient(#789F5B);
}
```

**CSS result by using Helpers**

```css
.selector {
	width: 32px;
	height: 32px;
	border-radius: 0px 0px 8px 8px;
	-webkit-border-radius: 0px 0px 8px 8px;
	-khtml-border-radius: 0px 0px 8px 8px;
	-moz-border-radius: 0px 0px 8px 8px;
	-ms-border-radius: 0px 0px 8px 8px;
	-o-border-radius: 0px 0px 8px 8px;
	background: linear-gradient(top, #93ae7f 0%, #5f8443 100%);
	background: -webkit-linear-gradient(top, #93ae7f 0%, #5f8443 100%);
	background: -khtml-linear-gradient(top, #93ae7f 0%, #5f8443 100%);
	background: -moz-linear-gradient(top, #93ae7f 0%, #5f8443 100%);
	background: -ms-linear-gradient(top, #93ae7f 0%, #5f8443 100%);
	background: -o-linear-gradient(top, #93ae7f 0%, #5f8443 100%);
	filter: progid:dximagetransform.microsoft.gradient(startColorstr='#93ae7f', endColorstr='#5f8443', GradientType=0);
}
```

###Modular state selectors

Frontsize has a tons of modular selectors dedicated to create a theme not just via CSS but also from your HTML template view, this can make you dramatically faster on changing the structure of your page without change a line of [LESS][1] or [SASS][2] code.

In the code below we'll use state selectors like `use-steps`, `vertical-padding` and `bottom-margin`:

```html
<div class="use-steps vertical-padding">
	<div class="bottom-margin widget-1">
		Some code here
	</div>
	<div class="widget-2">
		Some code here
	</div>
</div>
```

For more information, visit [modular state selectors](https://github.com/vitto/frontsize-less/wiki/State/) page.



##App configuration

The work of the front-end developer inside **Frontsize** starts from **app.less** file.

All the app configuration is here, where **Frontsize** global vars, grid and global rules and are stored.

Now we'll get a look on how it is by default:

```less
// font sizes for h# elements 
@h1: 2em;
@h2: 1.75em;
@h3: 1.5em;
@h4: 1.25em;
@h5: 1.125em;
@h6: 1em;

// Font sizes
@font-size: 1em;
@font-small-size: 0.75em;

// Fonts families global vars 
@font-sans:			'helvetica neue', helvetica, arial, sans-serif;
@font-serif:		georgia, 'times new roman', times, serif;
@font-monospace:	menlo, monaco, 'courier new', monospace;
@font-small:		'lucida grande', tahoma, verdana, arial, sans-serif;

// Default fonts used inside the core
@font-default: @font-sans;
@font-heading: @font-sans;
@font-line-height:	1.25;
@font-default-color: #7b8284;

// Global padding configuration
@horizontal-padding: 1em;
@vertical-padding: 1em;
@global-padding: @vertical-padding @horizontal-padding;

// State selectors configuration
@state-faded-opacity: 0.5;
@state-disabled-opacity: 0.5;
@state-table-padding: 0.5em;

// Set different width for the smartphones, tablets and hd resolutions
@smartphone-portrait-step:	320px;	// smartphones portrait		320~380
@smartphone-landscape-step:	480px;	// smartphones landscape	480~568~685
@tablet-portrait-step:		768px;	// tablet portrait			768
@tablet-landscape-step:		1024px;	// tablet landscape			1024
@hd-ready-step:				1280px;	// HD Ready					1280 (720p)
@hd-full-step:				1800px;	// Full HD					1920 (1080p)

// Sets the theme folder name where all theme code is located
@theme: 'theme';

// Enable or disable browser specific CSS3 prefixes
@use-css-prefix: true;

// Prepends the @rootpath var before every URL with .backgroundImage mixin
@use-rootpath: true;
@rootpath: 'frontsize-less/@{theme}/img/';

// This is 30kB more of CSS data, use it only if you need it
.useFrontsizeWidgets();

// Set font scaling to change the font size depending by different resolutions
.setFontScaling();

// Sets the Heading fonts scaling
.setHeadingFont();

// Creates a single CSS class with a font-family, font-size and font-smoothing properties for every viewport
.addFontsRule(with-small-fonts, @font-default, @font-small-size, antialiased, @font-default, 14px, antialiased, @font-default, 14px, antialiased);

// This mixin creates a container row to let the columns works best with a set of solid default behaviors
.addContainerRow(row);

// This mixin creates a complete set of rules based on three Frontsize media query viewports, starting from smartphone, to tablet and to hd viewports
.addColumnsSet(12);

// This mixin set a max-width to an HTML element depending by the current viewport and move it to the center of the page
.addViewportsSteps(use-steps, 500px, 100px, 50px, 0px);
```

##Grids




   [1]: http://lesscss.org/
   [2]: http://sass-lang.com/
   [3]: http://nodejs.org/
   [4]: https://npmjs.org/
   [5]: http://gruntjs.com/
   [6]: http://gruntjs.com/getting-started
   [7]: http://shapeshed.com/setting-up-nodejs-and-npm-on-mac-osx/
   [8]: http://frontsize.com/widgets
   [9]: http://smacss.com/book/type-state
  [10]: http://jonathanmh.com/make-grunt-watch-for-lesscss-changes/