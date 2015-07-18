# Simple Responsive Grid

Simple Responsive Grid is a responsive, mobile first fluid grid system that scales up to 6 columns as the device or viewport size increases and can be extended and nested as well. It includes predefined classes for easy layout options. It is inspired by [OOCSS](https://github.com/stubbornella/oocss/wiki/Grids) 

## Introduction

Grid systems are used for creating page layouts through a series of rows and columns that house your content. Here's how the simple responsive grid system works:

* Rows must be placed within a `.grid-wrap` -class for proper alignment and padding.
* Use the `.row` -class to create horizontal groups of columns
* Content should be placed within columns (`.col`), and only columns should be immediate children of rows
* Predefined grid classes like `.row` and e.g. `.g1-1of2` are available for quickly making grid layouts
* Columns create gutters (gaps between column content) via padding. That padding is offset in rows for the first and last column via negative margin on `.row`.
* Grid columns are specified by specifying the number columns, e.g. .size `.g-3of4` creates a column of that uses 75%. 
* if the space of column exceeds in total 100%, each group will wrap into a new line. (helper classes for clearfixing might be needed)
* Grid classes apply to devices with screen widths greater than or equal to the breakpoint sizes, and override grid classes targeted at smaller devices. Therefore, e.g. applying any `.g1-* class` to an element will not only affect its styling on medium devices but also on larger devices if a `.g2-* class` class is not present.

## Example

```
<div class="row">
	<div class="col g-1of1 g1-1of2">
		<!-- -->
	</div>
	<div class="col g-1of1 g1-1of2">
   		<!-- -->
	</div>
</div>	   		     	
```

The columns will be 100% on smallest viewports and switch to both 50% on the first breakpoint. (g1 is the first breakpoint, g2 the second etc.)

Grids can be nested. In this example on the nested row margin gutters are removed with the `.is-nested` class.

```
<div class="row">
	<div class="col g-1of1 g1-1of2">
		<!-- nested grid -->
   		<div class="row">
   			<div class="col g-1of1 g1-1of2">
   				<!-- -->
   			</div>	
   			<div class="col g-1of1 g1-1of2">
   				<!-- -->
   			</div>	
   		</div>
	</div>
	<div class="col g-1of1 g1-1of2">
   		<!-- -->
	</div>
</div>	   		     	
```

## Responsive Column Resets

With the of grids available you're bound to run into issues where, at certain breakpoints, your columns don't clear quite right as one is taller than the other. To fix that, use a combination of a .clearfix and the responsive utility classes.

```
<div class="row">
	<div class="col g-1of1 g1-1of2">
   		<!-- -->
	</div>
	<div class="g-block clearfix"></div>
	<div class="col g-1of1 g1-1of2">
   		<!-- -->
	</div>
</div>	   		     	
```

This example clears the float in the smallest viewport because g-1of1 and g-1of1 exceeding 100%. The g-block element will be hidden on any viewport > than g. 

## Offsetting colums

Columns can be offsetted. These classes increase the left margin of a column by * columns or %-value.

```
<div class="row">
	<div class="col g-1of1 g1-1of2 g-offset-1of2">
   		<!-- -->
	</div>
</div>	   		     	
```

In this example on the smallest viewport the column will show with 100% width and with the next breakpoint it will be shown with 50% and offsetted with 50%.

## DEMO

see it in [action](http://creinartz.github.io/responsive-grid)
