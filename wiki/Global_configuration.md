#Global configuration

The contents of this page are located in `frontsize/app.less`.

###Page index

- [Global vars](#global-vars)
	- [Environment](#environment)
	- [Padding & margin](#padding-and-margin)
	- [State](#state)
	- [Media query viewport global vars sizes](#media-query-viewport-global-vars-sizes)
- [Global mixins](#global-mixins)

#Global vars

All these vars should be used inside `frontsize/app.less`.

##Environment

Variable name           | Default value                 | Description
--- | --- | ---
`@theme`                | `theme`                       | The folder name of the theme you are using inside Frontsize environment
`@use-css-prefix`       | `true`                        | If set to `true` it adds all the cross browsers prefix to CSS3 properties, for example, `.box-shadow();` mixin will generate `box-shadow`, `-webkit-box-shadow`, `-khtml-box-shadow`, `-moz-box-shadow`, `-ms-box-shadow` and `-o-box-shadow`. If set to `false` it adds standard CSS3 property names only, for example, `.box-shadow();` mixin will generate `box-shadow` only
`@use-rootpath`         | `true`                        | Enables / disables `@rootpath` var inside `.backgroundImage` mixin
`@rootpath`             | `/css/frontsize/@{theme}/img` | This var is used inside the mixin `.backgroundImage` to keep consistent paths for background images

##Padding & margin

At the moment Frontsize uses the same vars for padding and margin.

Variable name           | Default value                             | Description
--- | --- | ---
`@horizontal-padding`   | `1em`                                     | This var is used around the core files for horizontal padding and margin
`@vertical-padding`     | `1em`                                     | This var is used around the core files for vertical padding and margin
`@global-padding`       | `@vertical-padding @horizontal-padding`   | This var is used around the core files for padding and margin

##State

State global vars will increase during next versions of Frontsize.

Variable name					| Default value	| Description
--- | --- | ---
`@state-faded-opacity`			| `0.5`			| Opacity for `.faded` *CSS* state selector
`@state-disabled-opacity`		| `0.5`			| Opacity for `.disabled` *CSS* state selector
`@state-table-padding`			| `0.5em`		| Padding for `.table` *CSS* state selector

##Media query viewport global vars sizes

The viewports available steps sizes, this shouldn't be changed if you want to keep the standard sizes.

Variable name					| Default value	| Description
--- | ---: | ---
`@smartphone-portrait-step`		| `320px`		| Viewport for smartphones portrait (320~380)
`@smartphone-landscape-step`	| `480px`		| Viewport for smartphones landscape (480~568~685)
`@tablet-portrait-step`			| `768px`		| Viewport for tablet portrait (768)
`@tablet-landscape-step`		| `1024px`		| Viewport for tablet landscape (1024)
`@hd-ready-step`				| `1280px`		| Viewport for HD Ready (1280, 720p)
`@hd-full-step`					| `1800px`		| Viewport for Full HD (1920, 1080p)

#Global mixins

All these mixins should be used once inside `frontsize/app.less`, this will ensure a more optimized filesize to the final CSS file.

Mixin name					| Description
--- | ---: | ---
`.addColumnsSet`			| This mixin creates a complete set of rules based on three Frontsize media query viewports, starting from smartphone, to tablet and to hd viewports, for more information visit [Grids page](https://github.com/vitto/frontsize-less/wiki/Grids#addColumnsSet)
`.addContainerRow`			| This mixin creates a container row to let the columns works best with a set of solid default behaviors, for more information visit [Grids page](https://github.com/vitto/frontsize-less/wiki/Grids#addContainerRow)
`.addFontsRule`				| Creates a single *CSS class* with a `font-family`, `font-size` and `font-smoothing` properties for every viewport, for more information visit [Fonts page](https://github.com/vitto/frontsize-less/wiki/Fonts#addFontsRule)
`.addViewportsSteps`		| This mixin set a `max-width` to an HTML element depending by the current viewport and move it to the center of the page, for more information visit [Grids page](https://github.com/vitto/frontsize-less/wiki/Grids#addViewportsSteps)
`.setHeadingFont`			| Sets the Heading fonts scaling, for more information visit [Fonts page](https://github.com/vitto/frontsize-less/wiki/Fonts#setHeadingFont)
`.setFontScaling`			| Sets a *CSS* `font-size` property on *HTML* `body` element for every viewport, for more information visit [Fonts page](https://github.com/vitto/frontsize-less/wiki/Fonts#setFontScaling)
`.useFrontsizeWidgets`		| This are `30kB` more of *CSS* styles from Frontsize default styles, use it only if you need it

