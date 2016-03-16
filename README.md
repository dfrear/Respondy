# Respondy
A light responsive SASS grid framework with a balance between automation and user input.

##To Do
* Document mixins and functions.
* Documen output classes.
* Make 'sizes' media queries more customizable.
* Mixin to add classes to 'sizes' defined media queries. `Respondy-media(lrg, .example { margin: auto 0; })`
* Maybe add exclude option to stop printing of specific size/column `exclude: (sml: 1 2 5, lrg: 1 4)`.

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

This map may contain any number of lists. The key of the maps will be the cell prefix. Each list should have the media query attribute followed by a value interpreted as a pixel value and converted to em units. 

Example:
```sass
sizes: (
	tiny: max-width 300,
	large: min-width 800,
	huge: min-width 1200
)
```
would create the following where columns: 2
```css
@media(min-width: 18.75em) {
	.tiny-1{
		width: 50%;
	}
	.tiny-2{
		width: 100%;
	}
}

@media(min-width: 50em) {
	.large-1{
		width: 50%;
	}
	.large-2{
		width: 100%;
	}
}

@media(min-width: 75em) {
	.huge-1{
		width: 50%;
	}
	.huge-2{
		width: 100%;
	}
}
```