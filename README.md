Retina Sprite Mapper Mixins
=========================

Example project for making retina sprites.

**Features:**

* x,y offset & padding
* adjustable pixel ratio
* auto-generation of classes (configurable prefix)
* optional dimensions

**@todo:**

* Add hover/focus/active options
* Allow for multiple sprite selectors to be compiled in single @media
* Add SVG support as primary option, and offer retina, then standard sprite as fallbacks

See [retina-sprites.scss](https://github.com/krisbulman/retina-sprite-mapper/blob/master/sass/_retina-sprites.scss) for implimentation & testing.

Requirements: Sass + Compass

Icons used in this example project are from [Iconic](https://github.com/somerandomdude/Iconic) by P.J. Onori // @[somerandomdude](https://github.com/somerandomdude). 

```ruby
/* Assign paths using standard Compass sprite method. */
$sprites: sprite-map("icons/*.png", $spacing: 1px); // import normal sprites
$sprites2x: sprite-map("icons-retina/*.png", $spacing: 2px); // import 2x sprites

/* Creates the sprite maps and placeholder classes used by the other mixins. */
@include generate-sprite-map($sprites, $sprites2x);

/* Allows for pre-defined auto-generated classes. */
@include retina-sprite-classes($sprites, $sprites2x, $prefix: 'icon-');

/* This method allows for selective sprite placement. */
.icon-target {
 @include retina-sprite-item('target', $sprites, $sprites2x);
}
```
