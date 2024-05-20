# SVG

## Positions

### The grid

For all elements, SVG uses a coordinate system or grid system similar to the one used by canvas. That is, the **top left** corner of the document is considered to be the point **`(0,0)`**, or **point of origin**. Positions are then measured in pixels from the top left corner, with the __positive x__ direction being to the __right__, and the __positive y__ direction being to the __bottom__.

```

  0
0 |------- X
  |
  |
  |
  Y

  

 ``` 

NOTE: that this is slightly different than the way you're taught to graph as a kid (**y axis is flipped**). However, this is the same way elements in HTML are positioned (By default, LTR documents are considered not the RTL documents which position X from right-to-left).

Example:
the follwing defines a rectangle from the upper left corner that spans `100px` to the _right_ and `100px` to the _bottom_.
```html
<rect x="0" y="0" width="100" height="100" />
```

### Defining the SVG canvas

The `width` and `height` properties define **how much space the image takes up in the browser**


The `viewBox` property defines a **coordinate system for the image elements**.

- The first two values in viewBox define the `top-left` coordinate in the image

- the last two define the _size_ from the _perspective of the image elements_ ,how the **image elements** think of the image **when they position themself.**

In case the size defined by `viewBox` does not match the `width` and the `height` properties, _then the image scales up or scales down_.


```html
<!-- a simple SVG canvas with 100x100px. One user unit equals one screen unit. -->
<svg width="100" height="100">…</svg>
```
```html
<!-- The whole SVG canvas here is 200px by 200px in size.
 However, the viewBox attribute defines the portion of that canvas to display. 
These 200x200 pixels display an area that starts at user unit (0,0) and spans 100x100 user units to the right and to the bottom. 
This effectively zooms in on the 100x100 unit area and enlarges the image to double size. -->
<svg width="200" height="200" viewBox="0 0 100 100">…</svg>
```




## Basic shapes

### Rectangle


The `<rect>` element draws a rectangle on the screen.
 There are six basic attributes that control the position and shape of the rectangles on screen. The one on the right has its rx and ry parameters set, giving it rounded corners. If they're not set, they default to 0.

* `x`
The x position of the top left corner of the rectangle.

* `y`
The y position of the top left corner of the rectangle.

* `width`
The width of the rectangle.

* `height`
The height of the rectangle.

* `rx`
The x radius of the corners of the rectangle.

* `ry`
The y radius of the corners of the rectangle.

```html
<rect x="10" y="10" width="30" height="30"/>
<rect x="60" y="10" rx="10" ry="10" width="30" height="30"/>
```

### Circle

The <circle> element draws a circle on the screen. It takes three basic parameters to determine the shape and size of the element.


* `r`
The radius of the circle.

* `cx`
The x position of the center of the circle.

* `cy`
The y position of the center of the circle.

```html
<circle cx="25" cy="75" r="20"/>
```

### Ellipse
An `<ellipse>` is a more general form of the `<circle>` element, where you can scale the x and y radius of the circle separately.

* `rx`
The x radius of the ellipse.

* `ry`
The y radius of the ellipse.

* `cx`
The x position of the center of the ellipse.

* `cy`
The y position of the center of the ellipse.


```html
<ellipse cx="75" cy="75" rx="20" ry="5"/>
```


### Line
The `<line>` element takes the positions of two points as parameters and draws a straight line between them.

* `x1`
The x position of point 1.

* `y1`
The y position of point 1.

* `x2`
The x position of point 2.

* `y2`
The y position of point 2.

```html
<line x1="10" x2="50" y1="110" y2="150" stroke="black" stroke-width="5"/>
```

### Polyline
A `<polyline>` is a group of connected straight lines. Since the list of points can get quite long, all the points are included in one attribute:

**points**

A list of points. Each number must be separated by a space, comma, EOL, or a line feed character with additional whitespace permitted. Each point must contain two numbers: an x coordinate and a y coordinate. So, the list (0,0), (1,1), and (2,2) could be written as 0, 0 1, 1 2, 2.

```html
<polyline points="60, 110 65, 120 70, 115 75, 130 80, 125 85, 140 90, 135 95, 150 100, 145"/>
```


### Polygon
A `<polygon>` is similar to a `<polyline>`, in that it is composed of straight line segments connecting a list of points. For polygons though, the path automatically connects the last point with the first, creating a closed shape.

**points**

A list of points, each number separated by a space, comma, EOL, or a line feed character with additional whitespace permitted. Each point must contain two numbers: an x coordinate and a y coordinate. So, the list (0,0), (1,1), and (2,2) could be written as 0, 0 1, 1 2, 2. The drawing then closes the path, so a final straight line would be drawn from (2,2) to (0,0).

```html
<polygon points="50, 160 55, 180 70, 180 60, 190 65, 205 50, 195 35, 205 40, 190 30, 180 45, 180"/>
```
### Path

A `<path>` is the most general shape that can be used in SVG. Using a path element, you can draw rectangles (with or without rounded corners), circles, ellipses, polylines, and polygons. Basically any of the other types of shapes, bezier curves, quadratic curves, and many more.


```html
<path d="M20,230 Q40,205 50,230 T90,230" fill="none" stroke="blue" stroke-width="5"/>
```

* `d`
A list of points and other information about how to draw the path.


### Examples

 <docs-code-multifile  preview  path="src/content/examples/svg/svg-tutorial/svg-tutorial.component.ts" >

<docs-code language="html" header="rect" visibleRegion="rect"  path="src/content/examples/svg/svg-tutorial/svg-tutorial.component.html"/>
<docs-code language="html" header="circle" visibleRegion="circle"  path="src/content/examples/svg/svg-tutorial/svg-tutorial.component.html"/>
<docs-code language="html" header="ellipse" visibleRegion="ellipse"  path="src/content/examples/svg/svg-tutorial/svg-tutorial.component.html"/>
<docs-code language="html" header="line" visibleRegion="line"  path="src/content/examples/svg/svg-tutorial/svg-tutorial.component.html"/>
<docs-code language="html" header="polyline" visibleRegion="polyline"  path="src/content/examples/svg/svg-tutorial/svg-tutorial.component.html"/>
<docs-code language="html" header="polygon" visibleRegion="polygon"  path="src/content/examples/svg/svg-tutorial/svg-tutorial.component.html"/>
<docs-code language="html" header="path" visibleRegion="path"  path="src/content/examples/svg/svg-tutorial/svg-tutorial.component.html"/>


</docs-code-multifile>


#### Build a House with SVG

Taken from Hunor Márton Borbély's [svg tutorial](https://svg-tutorial.com/svg/house)

We use circles, rectangles, lines, polylines, and polygons here.

**`polyline`** :The difference between a `polyline` and a `polygon` is that a `polygon` will always _close itself_, and the `polyline` will _stay open_.

<docs-code-multifile  preview  path="src/content/examples/svg/house.ts">
<docs-code language="html" header="wall"   path="src/content/examples/svg/house.ts" visibleLines="[11,12,28]" />
<docs-code language="html" header="roof"   path="src/content/examples/svg/house.ts"  visibleLines="[11,12,13,28]"/>
<docs-code language="html" header="door"   path="src/content/examples/svg/house.ts"  visibleLines="[11,12,13,14,15,28]"/>
<docs-code language="html" header="door-knob"   path="src/content/examples/svg/house.ts"  visibleLines="[11,12,13,14,15,16,28]"/>
<docs-code language="html" header="stair"   path="src/content/examples/svg/house.ts"visibleLines="[11,12,13,14,15,16,17,28]" />
<docs-code language="html" header="stair-2"   path="src/content/examples/svg/house.ts" visibleLines="[11,12,13,14,15,16,17,18,28]"/>
<docs-code language="html" header="window"   path="src/content/examples/svg/house.ts" visibleLines="[11,12,13,14,15,16,17,18,19,20,28]"/>
<docs-code language="html" header="window-line-1"   path="src/content/examples/svg/house.ts" visibleLines="[11,12,13,14,15,16,17,18,19,20,21,28]"/>
<docs-code language="html" header="window-line-2"   path="src/content/examples/svg/house.ts" visibleLines="[11,12,13,14,15,16,17,18,19,20,21,22,28]"/>
<docs-code language="html" header="window-sill"   path="src/content/examples/svg/house.ts" visibleLines="[11,12,13,14,15,16,17,18,19,20,21,22,23,28]"/>
<docs-code language="html" header="circle-window" preview  path="src/content/examples/svg/house.ts"  visibleLines="[11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,28]"/>
<docs-code language="html" header="window-line-1" preview  path="src/content/examples/svg/house.ts" visibleLines="[11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,28]"/>
<docs-code language="html" header="window-line-2" preview  path="src/content/examples/svg/house.ts" visibleLines="[11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28]"/>

</docs-code-multifile>


<docs-callout schedule title="Comming Soon ">

  <docs-pill-row>
    <docs-pill href="https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths" title="more on path"/>
    <docs-pill href="https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/SVG_and_CSS"  title="animating svg"/>


  </docs-pill-row>
</docs-callout>