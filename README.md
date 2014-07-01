catmullrom2bezier
=================

Catmull-Rom Spline to Bezier Spline Converter, from [Douglas Alan Schepers](http://schepers.cc/getting-to-the-point). Shepazu, if you want ownership of this repo, I'd be glad to transfer it to you.

This is an experimental extension of the SVG 'path' element syntax to 
allow Catmull-Rom splines, which differs from Bezier curves in that all
defined points on a Catmull-Rom spline are on the path itself.

This is intended to serve as a proof-of-concept toward inclusion of a 
Catmull-Rom path command into the SVG 2 specification.  As such, it is 
not production-ready, nor are the syntax or resulting rendering stable;
notably, it does not include a 'tension' parameter to allow the author 
to specify how tightly the path interpolates between points.  Feedback
on this and other aspects is welcome.
 
The syntax is as follows:

```
([number],[number])+  R([number],[number])+ ([number],[number])*
```

In other words, there must be at least one coordinate pair preceding the 
Catmull-Rom path segment (just as with any other path segment), followed
by the new path command 'R', followed by at least two coordinate pairs,
with as many optional subsequent coordinate pairs as desired.  
 
(As with path syntax in general, the numbers may be positive or negative 
floating-point values, and the delimiter is any combination of spaces 
with at most one comma.)

#License:
This code is available under the MIT or GPL licenses, and it takes 
inspiration from Maxim Shemanarev's Anti-Grain Geometry library.
