#Grids

The contents of this page are located in `frontsize/core/media_queries.less` and `frontsize/core/core.less`.

If you'd like to see some direct example, pls visit [Frontsize grids](http://frontsize.com/grids)

###Page index

- [Container](#addContainerRow)
- [Columns sets](#addColumnsSet)
- Viewport steps
	- [addColumnSet](#addColumnSet)
	- [addFillToColumnSet](#addFillToColumnSet)
	- [preventSmartphoneColumnSet](#preventSmartphoneColumnSet)
	- [addViewportsSteps](#addViewportsSteps)

##addContainerRow

This mixin creates a container row to let the columns works best with a set of solid default behaviors.

Parameter                     | Default value  | Description
--- | --- | ---
`@selector`                   | `row`          | The name of the CSS rule name
`@hdFullSteps`                | `0`            | The number of columns per row on **Full HD** viewport, if set to `0` the rule will set everything but will not set a default width to the children which will need rules from `addColumnsSet` mixin
`@hdReadySteps`               | `12`           | The number of columns per row on **HD Ready** viewport
`@tabletLandscapeSteps`       | `6`            | The number of columns per row on **Tablet Landscape** viewport
`@tabletPortraitSteps`        | `3`            | The number of columns per row on **Tablet Portrait** viewport
`@smartphoneLandscapeSteps`   | `1`            | The number of columns per row on **Smartphone Landscape** viewport
`@smartphonePortraitSteps`    | `1`            | The number of columns per row on **Smartphone Portrait** viewport

With the next example we'll create a base rule for containers, in this way the children columns will not be disposed automatically and will need column sizing rules created with `addColumnsSet`.

**LESS usage example**

```less
/* It's recommended to use it in app.less file, where all the rule sets should be stored */
.addContainerRow(row);
```

**CSS Result**

```css
.row,
.row *,
.row > * {
	box-sizing: border-box;
	-webkit-box-sizing: border-box;
	-khtml-box-sizing: border-box;
	-moz-box-sizing: border-box;
	-ms-box-sizing: border-box;
	-o-box-sizing: border-box;
}
.row {
	padding-top: 1em;
	width: 100%;
	overflow: auto;
	clear: both;
}
```

The next example will show how to create automatic column sizing rules, they can be easily overridded by `addColumnsSet` rules you create.

**LESS usage example**

```less
/* It's recommended to use it in app.less file, where all the rule sets should be stored */
.addContainerRow(row, 8, 8, 4, 4, 2, 1);
```

**CSS Result**

```css
.row,
.row *,
.row > * {
	box-sizing: border-box;
	-webkit-box-sizing: border-box;
	-khtml-box-sizing: border-box;
	-moz-box-sizing: border-box;
	-ms-box-sizing: border-box;
	-o-box-sizing: border-box;
}
.row {
	padding-top: 1em;
	width: 100%;
	overflow: auto;
	clear: both;
}
.row > * {
	min-height: 1px;
	padding-left: 1em;
	padding-right: 1em;
	padding-bottom: 1em;
	float: left;
	position: relative;
	width: 12.5%;
}
@media only screen and (min-width: 1px) and (max-width : 479px) {
	.row > * {
		width: 100%;
	}
	.row > *:nth-child(1n + 1) {
		clear: both;
	}
}
@media only screen and (min-width: 480px) and (max-width : 767px) {
	.row > * {
		width: 50%;
	}
	.row > *:nth-child(2n + 1) {
		clear: both;
	}
}
@media only screen and (min-width: 768px) and (max-width : 1023px), only print {
	.row > * {
		width: 25%;
	}
	.row > *:nth-child(4n + 1) {
		clear: both;
	}
}
@media only screen and (min-width: 1024px) and (max-width : 1279px) {
	.row > * {
		width: 25%;
	}
	.row > *:nth-child(4n + 1) {
		clear: both;
	}
}
@media only screen and (min-width: 1280px) and (max-width : 1799px) {
	.row > * {
		width: 12.5%;
	}
	.row > *:nth-child(8n + 1) {
		clear: both;
	}
}
@media only screen and (min-width: 1800px) {
	.row > * {
		width: 12.5%;
	}
	.row > *:nth-child(8n + 1) {
		clear: both;
	}
}
```

##addColumnsSet

This mixin creates a complete set of rules based on three Frontsize media query viewports, starting from smartphone, to tablet and to hd viewports.

Parameter                     | Default value             | Description
--- | --- | ---
`@steps`                      | `12`                      | The number of steps the rule set has, if `@steps` is set to 12, the method will create 12 steps `width` in `%`
`@hdViewportPrefix`           | `hd-`                     | The prefix of the **HD** viewports, if `@steps` is set to 12, the method will create 12 rules per viewport from `hd-1-of-12` to `hd-12-of-12` by default
`@tabletViewportPrefix`       | `tablet-`                 | The prefix of the **Tablet** viewports, if `@steps` is set to 12, the method will create 12 rules per viewport from `tablet-1-of-12` to `tablet-12-of-12` by default
`@smartphoneViewportPrefix`   | `smartphone-`             | The prefix of the **Smartphone** viewports, if `@steps` is set to 12, the method will create 12 rules per viewport from `smartphone-1-of-12` to `smartphone-12-of-12` by default
`@fillFromViewport`           | `"smartphone-landscape"`  | The viewport where the rules will go to `width` at `100%`, you can choose from `full-hd`, `hd-ready`, `tablet-landscape`, `tablet-portrait`, `smartphone-landscape` and `smartphone-portrait`
`@viewTotalColumns`           | `true`                    | If set to `true`, the mixin will prepend `@columnsSeparator` and the `@steps` at the end of the rules created, if `@steps` is set to 12 you'll get `-of-12`
`@columnsSeparator`           | `-of-`                    | You can customize the `@columnsSeparator` string between the current column and the total columns

**LESS usage example**

```less
/* It's recommended to use it in app.less file, where all the rule sets should be stored */
.addColumnsSet(12);
```

This will generate a complete set of rules: `.hd-1-of-12` to `.hd-12-of-12`, `.tablet-1-of-12` to `.tablet-12-of-12` and `.smartphone-1-of-12` to `.smartphone-12-of-12`.
Every viewport will prevail with it's own viewport couple to the other rule sets, this means that if you are viewing on a **Tablet portrait** viewport and you have an HTML elment like `<div class="hd-3-of-12 tablet-6-of-12"></div>` the rule `.tablet-6-of-12` will be used in place of `.hd-3-of-12`.

**LESS usage example**

```less
/* It's recommended to use it in app.less file, where all the rule sets should be stored */
.addColumnsSet(12, hd, tb, sm, "smartphone-landscape", true, of);
```

This will generate a complete set of rules: `.hd1of12` to `.hd12of12`, `.tb1of12` to `.tb12of12` and `.sm1of12` to `.sm12of12`.

**LESS usage example**

```less
/* It's recommended to use it in app.less file, where all the rule sets should be stored */
.addColumnsSet(12, hd-, tb-, sm-, "smartphone-landscape", false);
```

This will generate a complete set of rules: `.hd-1` to `.hd-12`, `.tb-1` to `.tb-12` and `.sm-1` to `.sm-12`.

**LESS usage example**

```less
/* It's recommended to use it in app.less file, where all the rule sets should be stored */
.addColumnsSet(12, hd_, tb_, sm_, "tablet-portrait", true, _);
```

This will generate a complete set of rules: `.hd_1_12` to `.hd_12_12`, `.tb_1_12` to `.tb_12_12` and `.sm_1_12` to `.sm_12_12`.

Notice that ew are using `"tablet-portrait"` as `@fillFromViewport` params, this means every rule will go to `width:100%;` except for smartphone rules, will still work with their original behavior.

##addColumnSet

This mixin creates a complete set of rules with a specific number of steps defined by `@steps` param.

Parameter                     | Default value             | Description
--- | --- | ---
`@selector`                   | `col-`                    | The prefix of the column set created
`@steps`                      | `12`                      | The number of steps the rule set has, if `@steps` is set to 12, the method will create 12 steps `width` in `%`
`@viewTotalColumns`           | `true`                    | If set to `true`, the mixin will prepend `@columnsSeparator` and the `@steps` at the end of the rules created, if `@steps` is set to 12 you'll get `-of-12`
`@columnsSeparator`           | `-of-`                    | You can customize the `@columnsSeparator` string between the current column and the total columns

This is the same of the previous mixin `addColumnsSet` but here you'll create only one rule set and you cannot set a `@fillFromViewport` params, to do it you can simply add [`addColumnSetWithFill`](#addColumnSetWithFill) mixin, or use the [Media queries sizing states](https://github.com/vitto/frontsize-less/wiki/Media_queries/#sizing) inside the HTML.

**LESS usage example**

```less
/* It's recommended to use it in app.less file, where all the rule sets should be stored */
.addColumnSet(col-, 12, true, -);
```

**HTML example**

```html
<div class="col-3-12 fill-till-tablet-portrait">
	hello world!
</div>
```

The next example generates a set of rules which starts with the prefix you set as `prefix-#-of-#`.

**LESS usage**

```
// This global var will be used inside the mixin
@horizontal-padding:1em;

// This is recommended inside app.less file with the rest of the configuration
.addColumnSet(simple, 4);
```

**CSS result**

```
.simple-4-of-4, .simple-3-of-4, .simple-2-of-4, .simple-1-of-4 {
	padding-left:1em;
	padding-right:1em;
	float: left;
	box-sizing: border-box;
	-webkit-box-sizing: border-box;
	-khtml-box-sizing: border-box;
	-moz-box-sizing: border-box;
	-ms-box-sizing: border-box;
	-o-box-sizing: border-box;
}
.simple-1-of-4 {
	width:25%;
}
.simple-2-of-4 {
	width:50%;
}
.simple-3-of-4 {
	width:75%;
}
.simple-4-of-4 {
	width:100%;
}

```

##addFillToColumnSet

This mixin set the `width` to `100%` to a rule set until a specific viewport in support of `addColumnSet`.

Parameter                     | Default value             | Description
--- | --- | ---
`@selector`                   | `col-`                    | The prefix of the column set created
`@steps`                      | `12`                      | The number of steps the rule set has, if `@steps` is set to 12, the method will create 12 steps `width` in `%`
`@fillFromViewport`           | `"smartphone-landscape"`  | The viewport where the rules will go to `width` at `100%`, you can choose from `tablet-landscape`, `tablet-portrait`, `smartphone-landscape` and `smartphone-portrait`
`@viewTotalColumns`           | `true`                    | If set to `true`, the mixin will prepend `@columnsSeparator` and the `@steps` at the end of the rules created, if `@steps` is set to 12 you'll get `-of-12`
`@columnsSeparator`           | `-of-`                    | You can customize the `@columnsSeparator` string between the current column and the total columns

**LESS usage**

```less
.addFillToColumnSet(step-, 4, "smartphone-landscape", true, -of-);
```

**CSS result**

```css
@media only screen and (max-width: 767px) {
  .step-4-of-4, .step-3-of-4, .step-2-of-4, .step-1-of-4 {
    width: 100%;
  }
}
```

##preventSmartphoneColumnSet

This is an internal mixin used by Frontsize inside `addColumnsSet`, it prevents smartphone viewport selectors to not be overridden by other viewport selector rules.

Parameter                     | Default value             | Description
--- | --- | ---
`@selector`                   | `col-`                    | The prefix of the column set created
`@totalSteps`                 | `12`                      | The number of steps the rule set has, if `@steps` is set to 12, the method will create 12 steps `width` in `%`
`@viewTotalColumns`           | `true`                    | If set to `true`, the mixin will prepend `@columnsSeparator` and the `@steps` at the end of the rules created, if `@steps` is set to 12 you'll get `-of-12`
`@columnsSeparator`           | `-of-`                    | You can customize the `@columnsSeparator` string between the current column and the total columns

**LESS usage**

```less
.preventSmartphoneColumnSet(col-, 7);
```

**CSS result**

```css
@media only screen and (max-width: 767px) {
  .col-7-of-7 {
    width: 100%;
  }
  .col-6-of-7 {
    width: 85.71428571428571%;
  }
  .col-5-of-7 {
    width: 71.42857142857143%;
  }
  .col-4-of-7 {
    width: 57.142857142857146%;
  }
  .col-3-of-7 {
    width: 42.857142857142854%;
  }
  .col-2-of-7 {
    width: 28.571428571428573%;
  }
  .col-1-of-7 {
    width: 14.285714285714286%;
  }
}
```


##addViewportsSteps

This mixin set a `max-width` to an HTML element depending by the current viewport and move it to the center of the page.

Parameter                     | Default value             | Description
--- | --- | ---
`@selector`                   | `use-steps`               | The selector name created
`@hdFullMargin`               | `500px`                   | Horizontal margin on **Full HD** viewport, it subtracts `@hdFullMargin` from the current viewport `width`.
`@hdReadyMargin`              | `100px`                   | Horizontal margin on **HD Ready** viewport, it subtracts `@hdReadyMargin` from the current viewport `width`.
`@tabletLandscapeMargin`      | `50px`                    | Horizontal margin on **Tablet Landscape** viewport, it subtracts `@tabletLandscapeMargin` from the current viewport `width`.
`@tabletPortraitMargin`       | `20px`                    | Horizontal margin on **Tablet Portrait** viewport, it subtracts `@tabletPortraitMargin` from the current viewport `width`.

**LESS usage**

```less
.addViewportsSteps(use-steps, 500px, 100px, 50px, 20px);
```

**CSS result**
```css
.use-steps {
	margin: auto;
	box-sizing: border-box;
	-webkit-box-sizing: border-box;
	-khtml-box-sizing: border-box;
	-moz-box-sizing: border-box;
	-ms-box-sizing: border-box;
	-o-box-sizing: border-box;
}
@media only screen and (min-width: 768px), only print {
	.use-steps {
		max-width: 768px;
	}
}
@media only screen and (min-width: 1024px) {
	.use-steps {
		max-width: 974px;
	}
}
@media only screen and (min-width: 1280px) {
	.use-steps {
		max-width: 1180px;
	}
}
@media only screen and (min-width: 1800px) {
	.use-steps {
		max-width: 1300px;
	}
}
```
