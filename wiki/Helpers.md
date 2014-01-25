#Helpers

Helpers are used in the **LESS** files inside your theme, these mixins can be useful to build a consistent layouts where everything is easy to be edited and fast to be created.

The contents of this page are located in `core/helpers.less`.

###Page index

- [Creating an helper](#creating-an-helper)
- [Background images](#background-images)
- [CSS3 Border radius](#css3-border-radius)
- [CSS3 Box shadow](#css3-box-shadow)
- [CSS3 Gradient](#css3-gradient)
- [Element behavior](#element-behavior)
- [Positioning](#positioning)
- [Sizing](#sizing)
- [Sprites](#sprites)
- [Tables](#tables)
- [Text](#text)
- [Transitions](#transitions)

##Creating an helper

In Frontsize, core Helpers are designed to perform multiple tasks in one call, this could be helpful for theme designers, let's make a simple example:

```less
.size(@width:16px, @height:@width, @scale:1) {
	width: @width * @scale;
	height: @height * @scale;
}
```

As you notice, you can set a default value taken from the previous parameters you pass, if `@height` is not defined it will get `@width` value.
Then you can call your mixin like in the example below.

```less
.css-class {
	.size(24px);
}
```

This mixin will result this CSS code:

```css
.css-class {
	width: 24px;
	height: 24px;
}
```

##Background images

Property mixin							| Default value																																																					| Description
-|-|-
`.backgroundHdFull`						| `@backgroundImage`:None																																																		| Sets the passed `background-image` *CSS property* from **Full HD viewport**
`.backgroundHdReady`					| `@backgroundImage`:None																																																		| Sets the passed `background-image` *CSS property* from **HD Ready viewport**
`.backgroundImage`						| `@backgroundImage`:None, `@path`:*''* or `@rootpath` depending by `@use-rootpath` setting																																		| Sets the `background-image` *CSS property* prepending the `@rootpath` var depending by `@use-rootpath` var
`.backgroundResponsive`					| `@hdFullBackground`:None, `@hdReadyBackground`:None, `@tabletLandscapeBackground`:None, `@tabletPortraitBackground`:None, `@smartphoneLandscapeBackground`:None, `@smartphonePortraitBackground`:None							| Sets a different `background-image` *CSS property* for every **viewport**
`.backgroundSmartphoneLandscape`		| `@backgroundImage`:None																																																		| Sets the passed `background-image` *CSS property* from **Smartphone Landscape viewport**
`.backgroundSmartphonePortrait`			| `@backgroundImage`:None																																																		| Sets the passed `background-image` *CSS property* from **Smartphone Portrait viewport**
`.backgroundTabletLandscape`			| `@backgroundImage`:None																																																		| Sets the passed `background-image` *CSS property* from **Tablet Landscape viewport**
`.backgroundTabletPortrait`				| `@backgroundImage`:None																																																		| Sets the passed `background-image` *CSS property* from **Tablet Portrait viewport**
`.icon`									| `@backgroundImage`:None, `@width`:None, `@height`:`@width`																																									| Sets the passed `background-image` *CSS property*, and a size with `width` and `height`, then sets `background-repeat` to `no-repeat` and `background-position` to `center`

##CSS3 Border radius

Property mixin		| Default value			| Description
-|-|-
`.roundBottom`		| `@radius`:*6px*		| Sets `border-radius` *CSS property* to `0px 0px @radius @radius`
`.roundLeft`		| `@radius`:*6px*		| Sets `border-radius` *CSS property* to `0px @radius @radius 0px`
`.roundRight`		| `@radius`:*6px*		| Sets `border-radius` *CSS property* to `@radius 0px 0px @radius`
`.roundTop`			| `@radius`:*6px*		| Sets `border-radius` *CSS property* to `@radius @radius 0px 0px`

##CSS3 Box shadow

Property mixin			| Default value															| Description
-|-|-
`.outlineBoxShadow`		| `@outlineOpacity`:*0.2*, `@boxShadow`:*0px 0px 0px transparent*		| Sets a `box-shadow` *CSS property* as outline, you can set the opacity ammouth passed and also an additional shadow to the *HTML element*

##CSS3 Gradient

Property mixin			| Default value																						| Description
-|-|-
`.glossGradient`			| `@top`:*rgb(200,200,200)*, `@middle`:*rgb(100,100,100)*, `@bottom`:*rgb(150,150,150)*				| Sets a gloss gradient to the *HTML element*
`.verticalGradient`			| `@color`:*#cbcbcb*, `@strenght`:*5%*																| Sets a vertical gradient to the *HTML element*, it's based on one single color and the strenght of the lightness and saturation, this mixin uses `saturate`, `lighten` and `darken` from **LESS** internal mixins
`.verticalGradientColors`	| `@firstColor`:*#000000*, `@lastColor`:*#FFFFFF*													| Sets a vertical gradient to the *HTML element*, it's based on the gradient between two colors

##Element behavior

Property mixin			| Default value					| Description
-|-|-
`.defaultElement`		| No parameters expected		| Sets the CSS3 `appearance` property to `none` and remove some default style set to the elements, it's usual for forms elements but it's buggy on Firefox, Opera, and obviously Internet Explorer
`.disableOutline`		| No parameters expected		| Removes the `outline` style from elements

##Positioning

Property mixin		| Default value									| Description
-|-|-
`.hooked`			| `@zIndex`:*100*								| Sets the `position` *CSS property* to `fixed`, `width` to `100%` and other properties, it's useful for nav menu fixed to top or to bottom.
`.moveBottom`		| `@bottom`:*0px*, `@position`:*relative*		| Sets the `position` *CSS property* to `relative` by default, and can move bottom the *HTML element*
`.moveLeft`			| `@left`:*0px*, `@position`:*relative*			| Sets the `position` *CSS property* to `relative` by default, and can move left the *HTML element*
`.moveRight`		| `@right`:*0px*, `@position`:*relative*		| Sets the `position` *CSS property* to `relative` by default, and can move right the *HTML element*
`.moveTop`			| `@top`:*0px*, `@position`:*relative*			| Sets the `position` *CSS property* to `relative` by default, and can move top the *HTML element*

##Sizing

Property mixin		| Default value								| Description
-|-|-
`.size`				| `@width`:*16px*, `@height`:`@width`, `@scale`:*1*		| Sets the size of an *HTML element* with `width` and `height` *CSS properties*

Note that the `scale` param can be a value between `0`, `1` or more, also decimals like `0.25` are allowed.

##Sprites

Property mixin				| Default value																						| Description
-|-|-
`.sprite`					| `@image`, `@width`, `@height`:`@width`, `@backgroudSize`:*auto*									| Prepares an *HTML element* to contain a background image ready to be used as sprite
`.spriteCoordinates`		| `@positionX`:*0px*, `@positionY`:*0px*															| Sets the coordinates of a sprite without need to use negative values
`.spritePosition`			| `@horizontalPosition`:*0*, `@verticalPosition`:*0*, `@width`:*0px*, `@height`:`@width`			| Sets integer position of a sprite by assuming the background image has modular size images inside

**How to use a sprite**
```less
/* app.less file */
@theme: 'my_theme';
@use-rootpath: true;
@rootpath: '/css/frontsize/@{theme}/img/';

/* Your view file */
.fruit {
	@size: 24px;
	.sprite("sprite-image.png", @size);
	&.lemon {
		.spritePosition(0, 0, @size);
	}
	&.pineapple {
		.spritePosition(1, 0, @size);
	}
	&.strawberry {
		.spritePosition(2, 0, @size);
	}
	&.cherry {
		.spritePosition(0, 1, @size);
	}
	&.pear {
		.spritePosition(1, 1, @size);
	}
	&.apple {
		.spritePosition(2, 1, @size);
	}
}
```

**CSS result**
```css
.fruit {
	background-image("/css/frontsize/my_theme/img/sprite-image.png");
	width: 24px;
	height: 24px;
}
.fruit.lemon {
	background-position: 0px 0px;
}
.fruit.pineapple {
	background-position: -24px 0px;
}
.fruit.strawberry {
	background-position: -48px 0px;
}
.fruit.cherry {
	background-position: 0px -24px;
}
.fruit.pear {
	background-position: -24px -24px;
}
.fruit.apple {
	background-position: -48px -24px;
}

```

##Tables

Property mixin		| Default value																			| Description
-|-|-
`.asTable`			| `@cellPadding`:`@global-padding`, `@verticalAlign`:*middle*, `@tableWidth`:*100%*		| Makes an *HTML elements* structure to behave as `table`
`.asTableCell`		| `@cellPadding`:`@global-padding`, `@verticalAlign`:*middle*							| Makes an *HTML elements* structure to behave as `table-row`
`.asTableRow`		| `@cellPadding`:`@global-padding`, `@verticalAlign`:*middle*							| Makes an *HTML element* to behave as `table-cell`

##Text

Property mixin		| Default value											| Description
-|-|-
`.cropText`			| `@overflow`:*ellipsis*, `@whiteSpace`:*nowrap*		| Makes an *HTML element* ready to crop text which overflows outsite it's container

##Transitions

Property mixin		| Default value											| Description
-|-|-
`.ease`				| `@easing`:None										| Expects a **Frontsize** ease function parameter

Available easing animations for `.ease` mixin

Easing 				| Description
-|-
`ease-in-back`		| Ease in back
`ease-in-circ`		| Ease in circular
`ease-in-cubic`		| Ease in cubic
`ease-in-expo`		| Ease in expo
`ease-in-quad`		| Ease in quadratic
`ease-in-quart`		| Ease in quartic
`ease-in-quint`		| Ease in quintic
`ease-in-sine`		| Ease in sine
`ease-out-back`		| Ease out back
`ease-out-circ`		| Ease out circular
`ease-out-cubic`	| Ease out cubic
`ease-out-expo`		| Ease out expo
`ease-out-quad`		| Ease out quadratic
`ease-out-quart`	| Ease out quartic
`ease-out-quint`	| Ease out quintic
`ease-out-sine`		| Ease out sine
`ease-in-out-back`	| Ease in out back
`ease-in-out-circ`	| Ease in out circular
`ease-in-out-cubic`	| Ease in out cubic
`ease-in-out-expo`	| Ease in out expo
`ease-in-out-quad`	| Ease in out quadratic
`ease-in-out-quart`	| Ease in out quartic
`ease-in-out-quint`	| Ease in out quintic
`ease-in-out-sine`	| Ease in out sine
