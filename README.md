# Respondy
A light responsive SASS grid framework with a balance between automation and user input.

##Options

###Defaults
A `@include Respondy()` with no options specified will be equivalent to:
```sass
@include Respondy((
	compatibility: false,
	content-width: 1000,
	columns: 12,
	padding: 10,
	base: true,
	offset: false,
	pushpull: false,
	vis: false,
	sizes: (
			sml: max-width 500,
			lrg: min-width 800
		)
))
```

###compatibility
**Type:** Boolean,
**Default:** `false`

**false**
The `padding` value will be interpreted as a pixel value and converted to em units.

**true**
Setting compatibility to true will make the `padding` value be interpreted as a percentage. This supports older browsers without support for `box-sizing: border-box`.

###content-width
**Type:** Number,
**Default:** `1000`

Sets the `max-width` of the `.row` class.

###columns
**Type:** Number,
**Default:** `12`

Specify the number of columns you want your grid to be divided into.

###padding
**Type:** Number,
**Default:** `10`

The left and right padding values interpreted as a pixel value and converted to em units.

###base
**Type:** Boolean,
**Default:** `true`

Setting this to true will include the standard grid.

###offset
**Type:** Boolean
**Default:** `false`

Setting this to true will include the offset system.

###pushpull
**Type:** Boolean,
**Default:** `false`

Setting this to true will include the pushpull system.

###vis
**Type:** Boolean,
**Default:** `false`

Setting this to true will include the vis system.

###sizes
**Type:** Map,
**Default:** `(sml: max-width 500, lrg: min-width 800)`

This map may contain any number of lists. The key of the maps will be the cell prefix. Each list should have the media query attribute by the value interpreted as a pixel value and converted to em units. 

Example:
```sass
	(extra: (break: 1200, type: min-width))
```
would create the following where columns: 2
```css
	@media(min-width: 75em) {
		.extra-1{
			width: 50%;
		}
		.extra-2{
			width: 100%;
		}
	}
```