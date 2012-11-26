# Home

This is a fork of Stefan Petre's [original code](http://www.eyecon.ro/bootstrap-colorpicker/);
thanks go to him for getting this thing started!

Please note that this fork is not used on Stefan's page at this time, nor is it maintained or
contributed to by him (yet?)

# About
Add color picker to field or to any other element.

* can be used as a component
* alpha picker
* multiple formats: hex, rgb, rgba, hsl, hsla

# Change log
* 29/9/2012
* Fixed issues on IE7-8 when using alpha
* Fixed issue when clicking on the preview
*Updated the docs with information about the color object

# Example

## Attached to a field with hex format specified via options.
######
	<input type="text" class="span1" value="#8fff00" id="cp1">
######

## Attached to a field with the rgba format specified via data tag.
######
	<input type="text" class="span3" value="rgb(0,194,255,0.78)" id="cp2" data-color-format="rgba">
######

## As component:
######
	<div class="input-append color" data-color="rgb(255, 146, 180)" data-color-format="rgb" id="cp3">
		<input type="text" class="span2" value="" readonly="">
		<span class="add-on"><i style="background-color: rgb(255, 146, 180);"></i></span>
	</div>
######
 
## Using events to work with the color.
######
	<a href="#" class="btn small" id="cp4" data-color-format="hex" data-color="rgb(255, 255, 255)">Change background color</a>
######

# Using bootstrap-colorpicker.js

## Call the colopicker via javascript:
######
	$('.colorpicker').colorpicker()
######

Options
* Name	type	default	description
* format	string	'hex'	the color format - hex | rgb | rgba.
* Markup
* Format a component.

######
	<div class="input-append color" data-color="rgb(255, 146, 180)" data-color-format="rgb">
	  <input type="text" class="span2" value="" >
	  <span class="add-on"><i style="background-color: rgb(255, 146, 180)"></i></span>
	</div>
######


###Methods

###.colorpicker(options)
Initializes an colorpicker.

###.colorpicker('show')
Show the color picker

###.colorpicker('hide')
Hide the color picker

###.colorpicker('place')
Updates the color picker's position relative to the element

###.colorpicker('setValue', value)
Set a new value for the color picker. Triggers 'changeColor' event.

##Color object methods
Each triggered events have a color object used internally by the picker. This object has several usefull methods.

###.setColor(value)
Set a new color. The value is parsed and tries to do a quess on the format.

###.setHue(value)
Set the HUE with a value between 0 and 1.

###.setSaturation(value)
Set the saturation with a value between 0 and 1.

###.setLightness(value)
Set the lightness with a value between 0 and 1.

###.setAlpha(value)
Set the transparency with a value between 0 and 1.

###.toRGB()
Returns a hash with red, green, blue and alpha.

###.toHex()
Returns a string with HEX format for the current color.

###.toHSL()
Returns a hash with HSLA values.

##Events
Colopicker class exposes a few events for manipulating the colors.

Event	Description
show	This event fires immediately when the color picker is displayed.
hide	This event is fired immediately when the color picker is hidden.
changeColor	This event is fired when the color is changed.

######
	$('.colorpicker').colorpicker().on('changeColor', function(ev){
	  bodyStyle.backgroundColor = ev.color.toHex();
	});
######