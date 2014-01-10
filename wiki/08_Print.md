#Print

Below you'll read how the framework will help you to print page without write a row of code.

The contents of this page are located in `core/print.less`.

###Page index

- [Default styles](#default-styles)
- [State selectors](#state-selectors)
- [Viewport pagination](#viewport-pagination)

##Default styles

To ensure a fast frontend develop, Frontsize will use a set of styles to avoid colors and to keep everything readable.

##State selectors

Selector			| Description
`not-on-print`		| The property `display` of the HTML element will be set to `hidden`
`on-print-only`		| The property `display` of the HTML element will be set to `hidden` if the current viewport is not for **print**, otherwise will be set to `block` or `inline-block` if the element has also `.inline` state selector set
`little-on-print`	| The property `width` of the HTML element will be set to `25%`
`half-on-print`		| The property `width` of the HTML element will be set to `50%`
`almost-on-print`	| The property `width` of the HTML element will be set to `75%`
`fill-on-print`		| The property `width` of the HTML element will be set to `100%`

##Viewport pagination

To ensure everything is paginated right Frontsize is set to use the *Tablet portrait* viewports for print too, so what you see on *Tablet portrait* is what you'll see in your printed page.

Print viewport | Description
-|-
`@from-tablet-portrait`		| Go to [Media queries section](https://github.com/vitto/frontsize-less/wiki/Media_Queries/#) to see how it works
`@only-tablet-portrait`		| Go to [Media queries section](https://github.com/vitto/frontsize-less/wiki/Media_Queries/#) to see how it works
`@till-tablet-portrait`		| Go to [Media queries section](https://github.com/vitto/frontsize-less/wiki/Media_Queries/#) to see how it works
