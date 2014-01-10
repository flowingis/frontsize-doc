#Frontsize
**Built to build**

Documentation for version 1.0.0

---

##Documentation index

**1. A basic guide to Frontsize**

- [Features](#features)
	- [Built to build](#built-to-build)
	- [TV Compatible](#tv-compatible)
	- [Fully configurable](#fully-configurable)
	- [Retina support for images](#retina-support-for-images)
	- Scalable fonts
	- Widget components
	- Helper mixins components
	- Mudular selectors
- LESS or SASS? Why not both?
	- LESS installation
	- Compile LESS to CSS
	- SASS installation
	- Compile SASS to CSS
- App configuration
	- Grid sets
	- Main containers
	- Fonts
- Grids
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

**2. CSS3**

- [Border](https://github.com/vitto/frontsize-less/wiki/CSS3/#border)
- [Filter](https://github.com/vitto/frontsize-less/wiki/CSS3/#filter)
- [Placeholder](https://github.com/vitto/frontsize-less/wiki/CSS3/#placeholder)
- [Text](https://github.com/vitto/frontsize-less/wiki/CSS3/#text)
- [2D Transform](https://github.com/vitto/frontsize-less/wiki/CSS3/#2d-transform)
- [3D Transform](https://github.com/vitto/frontsize-less/wiki/CSS3/#3d-transform)
- [Interaction](https://github.com/vitto/frontsize-less/wiki/CSS3/#interaction)
- [Image](https://github.com/vitto/frontsize-less/wiki/CSS3/#image)
- [Background image](https://github.com/vitto/frontsize-less/wiki/CSS3/#background-image)
- [Simple transform](https://github.com/vitto/frontsize-less/wiki/CSS3/#simple-transform)
- [Print](https://github.com/vitto/frontsize-less/wiki/CSS3/#print)

**3. Global configuration**

- [Global vars](https://github.com/vitto/frontsize-less/wiki/Global_configuration/#global-vars)
	- [Environment](https://github.com/vitto/frontsize-less/wiki/Global_configuration/#environment)
	- [Padding & margin](https://github.com/vitto/frontsize-less/wiki/Global_configuration/#padding-and-margin)
	- [State](https://github.com/vitto/frontsize-less/wiki/Global_configuration/#state)
	- [Media query viewport global vars sizes](https://github.com/vitto/frontsize-less/wiki/Global_configuration/#media-query-viewport-global-vars-sizes)
- [Global mixins](https://github.com/vitto/frontsize-less/wiki/Global_configuration/#global-mixins)

**4. Fonts**

- [Headings](https://github.com/vitto/frontsize-less/wiki/Fonts/#headings)
- [Families](https://github.com/vitto/frontsize-less/wiki/Fonts/#families)
- [Mixin](https://github.com/vitto/frontsize-less/wiki/Fonts/#mixin)

**5. Grids**

- [Container](https://github.com/vitto/frontsize-less/wiki/Grids#addContainerRow)
- [Columns sets](https://github.com/vitto/frontsize-less/wiki/Grids#addColumnsSet)
- Viewport steps
	- [addColumnSet](https://github.com/vitto/frontsize-less/wiki/Grids#addColumnSet)
	- [addColumnSetWithFill](https://github.com/vitto/frontsize-less/wiki/Grids#addColumnSetWithFill)
	- [preventSmartphoneColumnSet](https://github.com/vitto/frontsize-less/wiki/Grids#preventSmartphoneColumnSet)
	- [addViewportsSteps](https://github.com/vitto/frontsize-less/wiki/Grids#addViewportsSteps)

**6. Helpers**

- [Creating an helper](https://github.com/vitto/frontsize-less/wiki/Helpers/#creating-an-helper)
- [Background images](https://github.com/vitto/frontsize-less/wiki/Helpers/#background-images)
- [CSS3 Gradient](https://github.com/vitto/frontsize-less/wiki/Helpers/#css3-gradient)
- [CSS3 Border radius](https://github.com/vitto/frontsize-less/wiki/Helpers/#css3-border-radius)
- [CSS3 Box shadow](https://github.com/vitto/frontsize-less/wiki/Helpers/#css3-box-shadow)
- [Element behavior](https://github.com/vitto/frontsize-less/wiki/Helpers/#element-behavior)
- [Positioning](https://github.com/vitto/frontsize-less/wiki/Helpers/#positioning)
- [Sizing](https://github.com/vitto/frontsize-less/wiki/Helpers/#sizing)
- [Sprites](https://github.com/vitto/frontsize-less/wiki/Helpers/#sprites)
- [Tables](https://github.com/vitto/frontsize-less/wiki/Helpers/#tables)
- [Text](https://github.com/vitto/frontsize-less/wiki/Helpers/#text)
- [Transitions](https://github.com/vitto/frontsize-less/wiki/Helpers/#transitions)

**7. Media queries**

- [From a viewport](https://github.com/vitto/frontsize-less/wiki/Media_queries/#from-a-viewport)
- [To a viewport](https://github.com/vitto/frontsize-less/wiki/Media_queries/#to-a-viewport)
- [From a viewport To a viewport](https://github.com/vitto/frontsize-less/wiki/Media_queries/#from-a-viewport-to-a-viewport)
- [Retina viewport](https://github.com/vitto/frontsize-less/wiki/Media_queries/#retina-viewport)
- [Pixel density rules](https://github.com/vitto/frontsize-less/wiki/Media_queries/#pixel-density-rules)
- [State](https://github.com/vitto/frontsize-less/wiki/Media_queries/#state)
	- [Text](https://github.com/vitto/frontsize-less/wiki/Media_queries/#text)
	- [Sizing](https://github.com/vitto/frontsize-less/wiki/Media_queries/#sizing)
	- [Displaying](https://github.com/vitto/frontsize-less/wiki/Media_queries/#displaying)
	- [Positioning](https://github.com/vitto/frontsize-less/wiki/Media_queries/#positioning)
	- [Retina](https://github.com/vitto/frontsize-less/wiki/Media_queries/#retina)
- [Helper](https://github.com/vitto/frontsize-less/wiki/Media_queries/#helper)
	- [Background images](https://github.com/vitto/frontsize-less/wiki/Media_queries/#background-images)

**8. Print**

- [Default styles](https://github.com/vitto/frontsize-less/wiki/Print/#default-styles)
- [State selectors](https://github.com/vitto/frontsize-less/wiki/Print/#state-selectors)
- [Viewport pagination](https://github.com/vitto/frontsize-less/wiki/Print/#viewport-pagination)

**9. Retina helpers**

- [Background images](https://github.com/vitto/frontsize-less/wiki/Retina_helpers/#background-images)

**10. State**

- [Containers](https://github.com/vitto/frontsize-less/wiki/State/#containers)
- [Images](https://github.com/vitto/frontsize-less/wiki/State/#images)
- [Interaction](https://github.com/vitto/frontsize-less/wiki/State/#interaction)
- [Lists](https://github.com/vitto/frontsize-less/wiki/State/#lists)
- [Miscellaneous](https://github.com/vitto/frontsize-less/wiki/State/#miscellaneous)
- [Navigation](https://github.com/vitto/frontsize-less/wiki/State/#navigation)
- [Positioning](https://github.com/vitto/frontsize-less/wiki/State/#positioning)
- [Spacing](https://github.com/vitto/frontsize-less/wiki/State/#spacing)
- [Tables](https://github.com/vitto/frontsize-less/wiki/State/#tables)
- [Text](https://github.com/vitto/frontsize-less/wiki/State/#text)

**11. Widgets**

- [Creating a widget](https://github.com/vitto/frontsize-less/wiki/Widgets/#creating-a-widget)
- [Contribute](https://github.com/vitto/frontsize-less/wiki/Widgets/#contribute)
- [Default widgets](https://github.com/vitto/frontsize-less/wiki/Widgets/#default-widgets)
