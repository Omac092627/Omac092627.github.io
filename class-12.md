HTML:
  CHART JS
    What is it?
        Chart JS is a library that's used in javascript to make my life easier.

      INTEGRATION
        Chart.js can be integrated with plain JavaScript or with different module loaders. The examples below show how to load Chart.js in different systems.

        THE GRID
            Before we can start drawing, we need to talk about the canvas grid or coordinate space. Our HTML skeleton from the previous page had a canvas element 150 pixels wide and 150 pixels high. To the right, you see this canvas with the default grid overlayed. Normally 1 unit in the grid corresponds to 1 pixel on the canvas. The origin of this grid is positioned in the top left corner at coordinate (0,0). All elements are placed relative to this origin. So the position of the top left corner of the blue square becomes x pixels from the left and y pixels from the top, at coordinate (x,y). Later in this tutorial we'll see how we can translate the origin to a different position, rotate the grid and even scale it, but for now we'll stick to the default.


        Drawing rectangles
          Unlike SVG, <canvas> only supports two primitive shapes: rectangles and paths (lists of points connected by lines). All other shapes must be created by combining one or more paths. Luckily, we have an assortment of path drawing functions which make it possible to compose very complex shapes.

          First let's look at the rectangle. There are three functions that draw rectangles on the canvas:

          fillRect(x, y, width, height)
          Draws a filled rectangle.
          strokeRect(x, y, width, height)
          Draws a rectangular outline.
          clearRect(x, y, width, height)
          Clears the specified rectangular area, making it fully transparent.
          Each of these three functions takes the same parameters. x and y specify the position on the canvas (relative to the origin) of the top-left corner of the rectangle. width and height provide the rectangle's size.


          The fillRect() function draws a large black square 100 pixels on each side. The clearRect() function then erases a 60x60 pixel square from the center, and then strokeRect() is called to create a rectangular outline 50x50 pixels within the cleared square.

          Drawing paths
            Now let's look at paths. A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path, or even a subpath, can be closed. To make shapes using paths, we take some extra steps:

            First, you create the path.
            Then you use drawing commands to draw into the path.
            Once the path has been created, you can stroke or fill the path to render it.
            Here are the functions used to perform these steps:

            beginPath()
            Creates a new path. Once created, future drawing commands are directed into the path and used to build the path up.
            Path methods
            Methods to set different paths for objects.
            closePath()
            Adds a straight line to the path, going to the start of the current sub-path.
            stroke()
            Draws the shape by stroking its outline.
            fill()
            Draws a solid shape by filling the path's content area.
            The first step to create a path is to call the beginPath(). Internally, paths are stored as a list of sub-paths (lines, arcs, etc) which together form a shape. Every time this method is called, the list is reset and we can start drawing new shapes.

            Moving the pen
                One very useful function, which doesn't actually draw anything but becomes part of the path list described above, is the moveTo() function. You can probably best think of this as lifting a pen or pencil from one spot on a piece of paper and placing it on the next.

                moveTo(x, y)
                Moves the pen to the coordinates specified by x and y.
                When the canvas is initialized or beginPath() is called, you typically will want to use the moveTo() function to place the starting point somewhere else. We could also use moveTo() to draw unconnected paths. Take a look at the smiley face below.

                To try this for yourself, you can use the code snippet below. Just paste it into the draw() function we saw earlier.


          Lines
            For drawing straight lines, use the lineTo() method.

            lineTo(x, y)
            Draws a line from the current drawing position to the position specified by x and y.
            This method takes two arguments, x and y, which are the coordinates of the line's end point. The starting point is dependent on previously drawn paths, where the end point of the previous path is the starting point for the following, etc. The starting point can also be changed by using the moveTo() method.


          Bezier and quadratic curves
              The next type of paths available are Bézier curves, available in both cubic and quadratic varieties. These are generally used to draw complex organic shapes.

              quadraticCurveTo(cp1x, cp1y, x, y)
              Draws a quadratic Bézier curve from the current pen position to the end point specified by x and y, using the control point specified by cp1x and cp1y.
              bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)
              Draws a cubic Bézier curve from the current pen position to the end point specified by x and y, using the control points specified by (cp1x, cp1y) and (cp2x, cp2y).
              The difference between these can best be described using the image on the right. A quadratic Bézier curve has a start and an end point (blue dots) and just one control point (indicated by the red dot) while a cubic Bézier curve uses two control points.

              The x and y parameters in both of these methods are the coordinates of the end point. cp1x and cp1y are the coordinates of the first control point, and cp2x and cp2y are the coordinates of the second control point.

              Using quadratic and cubic Bézier curves can be quite challenging, because unlike vector drawing software like Adobe Illustrator, we don't have direct visual feedback as to what we're doing. This makes it pretty hard to draw complex shapes. In the following example, we'll be drawing some simple organic shapes, but if you have the time and, most of all, the patience, much more complex shapes can be created.

              There's nothing very difficult in these examples. In both cases we see a succession of curves being drawn which finally result in a complete shape.
