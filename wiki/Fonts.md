#Fonts

The contents of this page are located in `frontsize/app.less` and `frontsize/theme/extra/media_queries.less`.

###Page index

- [Headings](#headings)
- [Families](#families)
- [Mixin](#mixin)

##Headings

Global font sizes for `h1-h6` heading HTML elements.

Variable name       | Default value     | Description
--- | ---: | ---
`@h1`               | `2em`             | Sets the `font-size` for `h1` *HTML* elements
`@h2`               | `1.75em`          | Sets the `font-size` for `h2` *HTML* elements
`@h3`               | `1.5em`           | Sets the `font-size` for `h3` *HTML* elements
`@h4`               | `1.25em`          | Sets the `font-size` for `h4` *HTML* elements
`@h5`               | `1.125em`         | Sets the `font-size` for `h5` *HTML* elements
`@h6`               | `1em`             | Sets the `font-size` for `h6` *HTML* elements

##Families

Global variables for fonts families you can use around your framework environment.

Variable name       | Default value                                         | Description
--- | --- | ---
`@font-sans`        | `'helvetica neue', helvetica, arial, sans-serif`      | A global var which can be used around your workflow
`@font-serif`       | `georgia, 'times new roman', times, serif`            | A global var which can be used around your workflow
`@font-monospace`   | `menlo, monaco, 'courier new', monospace`             | A global var which can be used around your workflow
`@font-small`       | `'lucida grande', tahoma, verdana, arial, sans-serif` | A global var which can be used around your workflow
`@font-heading`     | `@font-default`                                       | A global var which can be used around your workflow
`@font-default`     | `@font-sans`                                          | This *var* is used by the core *less* files as default value


##Mixin
Various Mixins to make your fonts styles environment complete.


###setFontScaling
Sets a *CSS* `font-size` property on *HTML* `body` element for every viewport, this mixin should be used once in `app.less` file.
To let the mixin works at it's best, it's a good practice to use `@vertical-padding`, @horizontal-padding` and `@global-padding` with `em` units, this keep tha padding with proportional size relative to the current `font-size`.

Parameter                       | Default value                     | Description
--- | --- | ---
`@hdFullFontSize`               | `(@font-size + (@font-size / 2))` | The default value will set the `font-size` for **Full HD** viewport with  `@font-size` increased by it's half value
`@hdReadyFontSize`              | `(@font-size + (@font-size / 4))` | The default value will set the `font-size` for **HD Ready** viewport with  `@font-size` increased by it's quarter value
`@tabletLandscapeFontSize`      | `@font-size`                      | Sets the **Tablet Landscape** viewport `font-size`
`@tabletPortraitFontSize`       | `@font-size`                      | Sets the **Tablet Portrait** viewport `font-size`
`@smartphoneLandscapeFontSize`  | `@font-size`                      | Sets the **Smartphone Landscape** viewport `font-size`
`@smartphonePortraitFontSize`   | `@font-size`                      | Sets the **Smartphone Portrait** viewport `font-size`
`@lineHeightMultiplier`         | `@font-line-height`               | Sets the `line-height` for all viewports

#####Automatic usage example:

```less
@font-size: 1.125em;
@font-line-height: 1.45;

.setFontScaling();
```

**Manual usage example**

```less
.setFontScaling(
    1.5em,          // Font size for Full HD
    1.25em,         // Font size for HD Ready
    1.125em,        // Font size for Tablet Landscape
    1em,            // Font size for Tablet Portrait
    0.875em,        // Font size for Smartphone Landscape
    0.875em,        // Font size for Smartphone Portrait
);
```

###setHeadingFont
Sets a *CSS* `font-size` property on *HTML* `h1-h6` elements for every viewport, this mixin should be used once in **app.less** file.

Parameter                       | Default value     | Description
--- | ---: | ---
`@hdFullFontSize`               | `1.5em`           | Sets the **Full HD** viewport `font-size`
`@hdReadyFontSize`              | `1.25em`          | Sets the **HD Ready** viewport `font-size`
`@tabletLandscapeFontSize`      | `1.125em`         | Sets the **Tablet Landscape** viewport `font-size`
`@tabletPortraitFontSize`       | `1.125em`         | Sets the **Tablet Portrait** viewport `font-size`
`@smartphoneLandscapeFontSize`  | `1em`             | Sets the **Smartphone Landscape** viewport `font-size`
`@smartphonePortraitFontSize`   | `1em`             | Sets the **Smartphone Portrait** viewport `font-size`

**LESS inline example**

```less
.setHeadingFont(2em, 1.875em, 1.75em, 1.5em, 1.375em, 1.25em);
```

###.addFontsRule
Creates a single *CSS class* with a `font-family`, `font-size` and `font-smoothing` properties for every viewport, this mixin is recommended to be used only in **app.less** file.

Parameter                   | Default value             | Description
--- | --- | ---
`@selector`                 | `with-small-fonts`        | Frontsize will add the `.` dot before the class name for you
`@fontFamilyHd`             | `@font-small`             | Sets the **HD** viewports `font-family`
`@fontSizeHd`               | `0.75em`                  | Sets the **HD** viewports `font-size`
`@antialiasHd`              | `antialiased`             | Sets the **HD** viewports `font-smoothing` (used by **Google Chrome** only)
`@fontFamilyTablet`         | `@font-small`             | Sets the **Tablet** viewports `font-family`
`@fontSizeTablet`           | `0.75em`                  | Sets the **Tablet** viewports `font-size`
`@antialiasTablet`          | `antialiased`             | Sets the **Tablet** viewports `font-smoothing` (used by **Google Chrome** only)
`@fontFamilySmartphone`     | `@font-small`             | Sets the **Smartphone** viewports `font-family`
`@fontSizeSmartphone`       | `0.85em`                  | Sets the **Smartphone** viewports `font-size`
`@antialiasSmartphone`      | `subpixel-antialiased`    | Sets the **Smartphone** viewports `font-smoothing` (used by **Google Chrome** only). The default antialias type for all browsers is set to `subpixel-antialiased`, little bit better for smaller fonts

**LESS usage example**

```less
@fontTurboBigHd: 'Helvetica Black', Helvetica, Arial, sans-serif;
@fontTurboBigTablet: 'Helvetica Bold', Helvetica, Arial, sans-serif;
@fontTurboBigSmartphone: 'Helvetica Medium', Helvetica, Arial, sans-serif;

.addFontsRule(
    turbo-big-font,
    @fontTurboBigHd, 2em, antialiased,
    @fontTurboBigTablet, 1.5em, antialiased,
    @fontTurboBigSmartphone, 1.25em, subpixel-antialiased
);
```

###.addFontRule
Creates a single *CSS class* with a `font-family`, `font-size` and `font-smoothing` properties for every viewport, this mixin is recommended to be used only in **app.less** file.

Parameter                       | Default value     | Description
--- | --- | ---
`@selector`                     | required          | Frontsize will add the `.` dot before the class name for you
`@fontFamily`                   | `@font-default`   | The `font-family` property for all viewports
`@hdFullFontSize`               | `1em`             | Sets the **Full HD** viewport `font-size`
`@hdReadyFontSize`              | `1em`             | Sets the **HD Ready** viewport `font-size`
`@tabletLandscapeFontSize`      | `1em`             | Sets the **Tablet Landscape** viewport `font-size`
`@tabletPortraitFontSize`       | `1em`             | Sets the **Tablet Portrait** viewport `font-size`
`@smartphoneLandscapeFontSize`  | `1em`             | Sets the **Smartphone Landscape** viewport `font-size`
`@smartphonePortraitFontSize`   | `1em`             | Sets the **Smartphone Portrait** viewport `font-size`
`@antialias`                    | `antialiased`     | Sets the `font-smoothing` for all viewports
`@lineHeightMultiplier`         | `1.225`           | Sets the `line-height` for all viewports

**LESS usage example**

```less
@fontComic: 'Different Comic Sans Family', 'Comic Sans MS', cursive, sans-serif;

.addFontRule(
    comic,          // CSS selector: <p class="comic">Hello world!</p>
    @fontComic,     // Font family
    1.5em,          // Font size for Full HD
    1.25em,         // Font size for HD Ready
    1.125em,        // Font size for Tablet Landscape
    1em,            // Font size for Tablet Portrait
    1em,            // Font size for Smartphone Landscape
    1em,            // Font size for Smartphone Portrait
    antialiased,    // Font smoothing
    1.5             // Font line height
);
```

**LESS inline example**

```less
@fontComic: 'Different Comic Sans Family', 'Comic Sans MS', cursive, sans-serif;
.addFontRule(comic, @fontComic, 1.5em, 1.25em, 1.125em, 1em, 1em, 1em, antialiased, 1.5);
```
