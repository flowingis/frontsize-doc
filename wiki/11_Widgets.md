#Widgets

The contents of this page are located in `core/widgets.less`.

###Page index

- [Creating a widget](#creating-a-widget)
- [Contribute](#contribute)
- [Default widgets](#default-widgets)

##Creating a widget

Widgets are thought as reusable *HTML* blocks with a defined structure and styled inside your theme folder `frontsize/theme/components/widgets.less`, they can be used more than once around the site and can be also varied by calling the widget mixin and passing different params to it.

Now let's create three simple social buttons to login into your website:

```
<a class="facebook-account" href="#">Connect with <span>Google+</span></a>
<a class="twitter-account top-margin" href="#">Connect with <strong>Twitter</strong></a>
<a class="google-account top-margin" href="#">Connect with <span>Google+</span></a>
<a class="github-account top-margin" href="#">Connect with <strong>GitHub</strong></a>
```

The widget `.button-account` is already present inside *Frontsize* by default, it can help to create these buttons. It expects three vars (which can be skipped) to theme your button with the right colors but mantain the template base styles like `padding`, `border-radius` and so on:

```
.button-account(@backgroundColor:#C3C3C3, @color:white, @textShadowColor:0px -1px 0px rgba(255, 0, 0, 0.3)) {
	
	display: inline-block;
	padding:0 0.5em;
	cursor:pointer;
	color:desaturate(lighten(@backgroundColor,25%),12%);
	text-shadow:0px -1px 0px rgba(0, 0, 0, 0.3);
	border:1px solid saturate(darken(@backgroundColor, 8%),8%);
	border-bottom-color:saturate(darken(@backgroundColor, 20%),20%);
	background-color: @backgroundColor;
	.border-radius(4px);
	.box-shadow(0px 2px 3px -2px rgba(0, 0, 0, 0.7), inset 0px 1px 0px rgba(255, 255, 255, 0.35););
	.transition(color .25s ease-out, box-shadow .25s ease-out;);
	.verticalGradient(@backgroundColor, 10%);
	
	> * {
		text-shadow:0px -1px 0px @textShadowColor;
		color:@color;
	}
	
	&:hover {
		text-shadow:0px -1px 0px @textShadowColor;
		color:@color;
		.verticalGradient(@backgroundColor, 0%);
	}
}
```

Then, you can assign the mixin call `.button-account` to a list of CSS classes selectors and pass the colours you need to make the differences you need:

```
.facebook-account {
	.button-account(#5670a6);
}
.google-account {
	.button-account(#d55a4a);
}
.twitter-account {
	.button-account(#53bbef);
}
.github-account {
	.button-account(#cdcdcd, darken(grey,15%), rgba(255,255,255,.3));
}
```

It's a good practice to store all your widgets in `frontsize/theme/components/widgets.less` without touch the core ones.

##Contribute

If you'd like to try before use it browse community widgets at [Frontsize widgets](http://frontsize.com/widgets/index).
You can create your own ones, make them public or private as you whish.

##Default widgets

Note that this widget is already working, just go to `frontsize/theme/components/widgets.less` to make the changes you need, this is a core widget and you'll find the mixin inside `frontsize/core/widgets.less`.
Below you can see a list of already working widgets:

Widget mixin 			| Default params 																																																							| Description
-|-|-
`.area-hifi`			| `@hifiColor`:*#3d4041*																																																					| Used as *header translucent area* in [Frontsize website](http://frontsize.com)
`.button-account`		| `@backgroundColor`:*#C3C3C3*, `@color`:*white*, `@textShadowColor`:*0px -1px 0px rgba(255, 0, 0, 0.3)*																																	| Makes *login buttons* for the various social networks
`.button-hifi`			| `@hifiColor`:*#3d4041*, `@color`:*#b1b1b1*																																																| Used as *header buttons* in [Frontsize website](http://frontsize.com)
`.button-box`			| `@backgroundColor`:*#1BA6DA*, `@padding`:*1em*, `@borderRadius`:*4px*																																										| Used as *download button* in the front page in [Frontsize website](http://frontsize.com)
`.button-mini`			| `@color`:*#E9E9E9*, `@textColor`:*darken(@color,40%)*																																														| Used as *download button* in the pages footer in [Frontsize website](http://frontsize.com)
`.button-metal`			| `@backgroundColor`:*#E2E4E3*, `@color`:*#535353*																																															| Used as *form button* around forms in [Frontsize website](http://frontsize.com)
`.button-dark-metal`	| `@backgroundColor`:*#414548*, `@color`:*#c3c3c5*, `@radius`:*4px*																																											| Thought as *form button* for forms around [Frontsize website](http://frontsize.com)
`.keyboard`				| `@color`:*#393634*, `@textColor`:*white*																																																	| Styles an HTML element as a *keyboard button* with a modern minimal colors
`.keyboard-vintage`		| `@color`:*#423F38*, `@textColor`:*white*																																																	| Styles an HTML element as a *keyboard button* with a vingate shape
`.keyboard-commodore`	| `@color`:*#CECBBA*, `@textColor`:*#423F38*																																																| Styles an HTML element as a *keyboard button* with **Commodore64** style
`.message-status`		| `@color`:*#DE6646*, `@backgroundColor`:*desaturate(lighten(`@color`,30%),30%)*, `@border`:*1px solid rgba(0,0,0,0.015)*, `@borderRadius`:*0.25em*, `@boxShadow`:*0px 1px 3px rgba(0,0,0,0.075)*, `@margin`:*0 0 `@vertical-padding` 0*	| Styles an HTML elements structure as *status message* stimilar to a **Growl notification**, but with a black translucent window
`.paginator-circular`	| `@containerLinkPadding`:*0 0.5em*, `@linkPadding`:*0.5em 0.875em*, `@backgroundColor`:*white*, `@color`:*#7b8284*, `@border`:*1px solid*, `@borderColor`:*#e2e2e2*, `@borderRadius`:*200px*												| Used as *paginator* in the current [Frontsize website](http://frontsize.com)
`.pic`					| `@borderWidth`:*3px*, `@boxShadow`:*0px 2px 3px rgba(0,0,0,0.2)*, `@outlineOpacity`:*0.2*																																					| Styles an HTML element as a framed picture
`.switch`				| `@borderRadius`:*6px*, `@padding`:*1px*, `@margin`:*2.5em*, `@onColor`:*#1BA6DA*, `@offColor`:*#DC3151*																																	| Styles switch buttons similar to iPhone, it requires JavaScript code to change their state
`.tabs`					| `@selectedColor`:*#7B8284*, `@selectedBackground`:*white*, `@defaultColor`:*#CCCCCC*, `@borderColor`:*#CCCCCC*, `@borderRadius`:*0.5em*, `@borderSize`:*1px*																				| Used as *navigation tabs* in [Frontsize website](http://frontsize.com)
`.text-buried`			| `@color`:*black*, `@light`:*rgba(255,255,255,.05)*, `@offset`:*1px*																																										| Styles a text inside an HTML element with a buried effect, it's used for frontsize title in the front page on [Frontsize website](http://frontsize.com)

#Enable / Disable core widgets

Core widgets can be useful if you just want to use the styles elements for buttons, header, social buttons, etc.
If you don't need them and want to decrease the filesize of the CSS exported, comment `.useFrontsizeWidgets()` located in `frontsize/app.less` to gain **30kB** filesize approx.
