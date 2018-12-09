# sassy
SASS - responsive

declare variables
----------------------
$variable_name : value

declare sass map
----------------------
$colors : (
  primary:#005dff,
  primary-lighten: lighten(#005dff, 40%)
)
Use it like below:
---------------------
body {
  background-color: map-get($color, primary)
}

functions in SASS
--------------------
@function color($color-name){
  @return map-get($color, $color-name)
}

use it like below
------------------
body:{
  background-color:color(primary)
}

Mixins:
--------

Mixins are used to group certain CSS property together based on some rule,
so that they can be applied easily througout the application without having 
to specify the rule again and again

Ex-> create a css rule for media query break point and use it through out the application. 
$desktop: 840px
@mixin <mixin name> {
  @media(min-width: #{$desktop}) {
    @content;
  }
}

usage
--------
@include <minxin name> {
  css-properties
}

Nesting in SASS
------------------------
Nesting in SASS refers to the way nested elements in a html is referred in .scss file.

Suppose if you have a button inside the body tag you can directly refere to it like below:

body {
  button {
    display: inline-block
  }
}

This will create a corresponding css of:

body button {
  display: inline-block
}
-------------------------
create clips
-------------------------
https://bennettfeely.com/clippy/

Ex-> clip-path: polygon(100% 0, 100% 50%, 65% 100%, 0 100%, 0 0);

Ccreates a CSS like this
-------------------------------------------------------------

    -webkit-clip-path: polygon(0 0, 72% 0, 57% 100%, 0% 100%);
            clip-path: polygon(0 0, 72% 0, 57% 100%, 0% 100%);
