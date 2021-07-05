## chart
Charts are far better for displaying data visually
- A great way to get started with charts is with Chart.js, a JavaScript plugin that uses HTML5’s canvas element to draw the graph onto the page
- The first thing we need to do is download Chart.js. Copy the Chart.min.js out of the unzipped folder and into the directory you’ll be working in. Then create a new html page and import the script

- **Drawing a line chart **
  - create a canvas element
  - write a script that will retrieve the context of the canvas
  - Inside the same script tags we need to create our data, in this instance it’s an object that contains labels for the base of our chart and datasets to describe the values on the chart.
  - Add this immediately above the line that begins ‘var buyers=’:
 
## Chart.js
  - t's easy to get started with Chart.js. All that's required is the script included in your page along with a single <canvas> node to render the chart.

## The <canvas> element
- At first sight a <canvas> looks like the <img> element, with the only clear difference being that it doesn't have the src and alt attributes. Indeed, the <canvas> element has only two attributes, width and height
-  for <video>, <audio>, or <picture> elements, it is easy to define some fallback content, to be displayed in older browsers not supporting it, like versions of Internet Explorer earlier than version 9 or textual browsers
-  the <canvas> element requires the closing tag (</canvas>)
- Scripts can also check for support programmatically by testing for the presence of the getContext() method. 
- The script includes a function called draw(), which is executed once the page finishes loading; this is done by listening for the load event on the document. 

## Drawing shapes with canvas
- The grid
- Drawing rectangles:
  - fillRect(x, y, width, height)
Draws a filled rectangle.
  - strokeRect(x, y, width, height)
Draws a rectangular outline.
  - clearRect(x, y, width, height)
Clears the specified rectangular area, making it fully transparent.
- Drawing paths :A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path, or even a subpath, can be closed
- Here are the functions used to perform these steps:
  - beginPath()
Creates a new path. Once created, future drawing commands are directed into the path and used to build the path up.
  - Path methods
Methods to set different paths for objects.
  - closePath()
Adds a straight line to the path, going to the start of the current sub-path.
  - stroke()
Draws the shape by stroking its outline.
  - fill()
Draws a solid shape by filling the path's content area.
- Drawing a triangle
- Moving the pen
- moveTo() function. You can probably best think of this as lifting a pen or pencil from one spot on a piece of paper and placing it on the next.
  - moveTo(x, y) Moves the pen to the coordinates specified by x and y.
- Lines For drawing straight lines, use the lineTo() method.

- lineTo(x, y) Draws a line from the current drawing position to the position specified by x and y.
- Arcs 
To draw arcs or circles, we use the arc() or arcTo() methods.
  - arc(x, y, radius, startAngle, endAngle, counterclockwise)
Draws an arc which is centered at (x, y) position with radius r starting at startAngle and ending at endAngle going in the given direction indicated by counterclockwise (defaulting to clockwise).
  - arcTo(x1, y1, x2, y2, radius)
Draws an arc with the given control points and radius, connected to the previous point by a straight line.
- Bezier and quadratic curves
The next type of paths available are Bézier curves, available in both cubic and quadratic varieties. These are generally used to draw complex organic shapes.

  - quadraticCurveTo(cp1x, cp1y, x, y)
Draws a quadratic Bézier curve from the current pen position to the end point specified by x and y, using the control point specified by cp1x and cp1y.
  - bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)
Draws a cubic Bézier curve from the current pen position to the end point specified by x and y, using the control points specified by (cp1x, cp1y) and (cp2x, cp2y).

- Path2D()
The Path2D() constructor returns a newly instantiated Path2D object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of SVG path data.



## Applying styles and colors
- If we want to apply colors to a shape, there are two important properties we can use: fillStyle and strokeStyle.
 
  - fillStyle = color
Sets the style used when filling shapes.
  - strokeStyle = color
Sets the style for shapes' outlines.
- Line styles :There are several properties which allow us to style lines.

  - lineWidth = value
Sets the width of lines drawn in the future.
  - lineCap = type
Sets the appearance of the ends of lines.
  - lineJoin = type
Sets the appearance of the "corners" where lines meet.
  - miterLimit = value
Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.
  - getLineDash()
Returns the current line dash pattern array containing an even number of non-negative numbers.
  - setLineDash(segments)
Sets the current line dash pattern.
  - lineDashOffset = value
Specifies where to start a dash array on a line.
- **Gradients**
we can fill and stroke shapes using linear, radial and conic gradient

- We create a CanvasGradient object by using one of the following methods. We can then assign this object to the fillStyle or strokeStyle properties.

  - createLinearGradient(x1, y1, x2, y2)
  - createRadialGradient(x1, y1, r1, x2, y2, r2)
  - createConicGradient(angle, x, y)
  - gradient.addColorStop(position, color)
 
- **Patterns**
we used a series of loops to create a pattern of images. There is, however, a much simpler method: the createPattern() method.
The type specifies how to use the image in order to create the pattern, and must be one of the following string values:

  - repeat
Tiles the image in both vertical and horizontal directions.
  - repeat-x
Tiles the image horizontally but not vertically.
  - repeat-y
Tiles the image vertically but not horizontally.
  - no-repeat
Doesn't tile the image. It's used only once.

** shadows**
Using shadows involves just four properties:
  - shadowOffsetX = float
Indicates the horizontal distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
  - shadowOffsetY = float
Indicates the vertical distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
  - shadowBlur = float
Indicates the size of the blurring effect; this value doesn't correspond to a number of pixels and is not affected by the current transformation matrix. The default value is 0.
  - shadowColor = color
A standard CSS color value indicating the color of the shadow effect; by default, it is fully-transparent black.

- **Canvas fill rules** :
When using fill (or clip and isPointInPath) you can optionally provide a fill rule algorithm by which to determine if a point is inside or outside a path and thus if it gets filled or not. This is useful when a path intersects itself or is nested.

Two values are possible:

  - "nonzero": The non-zero winding rule, which is the default rule.
  - "evenodd": The even-odd winding rule
