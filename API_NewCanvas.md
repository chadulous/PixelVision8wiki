# NewCanvas

The canvas is a special `TextureData` derivative that supports drawing primitive shapes such as lines, circles, and rectangles. You can also draw sprites and text to it as well. When you are done drawing on the canvas, you can copy the pixel data into the `SpriteChip `or directly to the tilemap cache. While the canvas allows run-time drawing, it’s not part of the core Pixel Vision 8 API. The canvas is used to create the tilemap cache and the additional drawing APIs, which are used by Pixel Vision OS, should be used sparingly since they could impact performance.

In order to draw on the canvas, you first need to set a stroke that represents the size of the brush and color to use. You can also set a pattern that is used to fill primitives such as the circle and rectangle. These patterns could be solid colors or graphics that will repeat within the boundaries of the shape. Each time you change the stroke or pattern, the next primitive that is drawn will reflect the changes.

## Usage

`NewCanvas ( w, h )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>w</td>
    <td>int</td>
    <td>The width value of the canvas as an int.</td>
  </tr>
  <tr>
    <td>h</td>
    <td>int</td>
    <td>The height value of the canvas as an int.</td>
  </tr>
</table>


## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Rect</td>
    <td>Returns a new instance of a Canvas to be used as a Lua object.</td>
  </tr>
</table>


## Drawing APIs

The Canvas has its own set of drawing APIs that allow you to draw pixel data to it. These are a few of the more common ones you can use.

<table>
  <tr>
    <td>Name</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Clear( colorID )</td>
    <td>Clears the canvas with the supplied color.</td>
  </tr>
  <tr>
    <td>DrawCentered( newValue )</td>
    <td>Defines if the drawing will use a center point when drawing circles and ellipses.</td>
  </tr>
  <tr>
    <td>DrawCircle( x0, y0, x1, y1, fill )</td>
    <td>Draws a circle between two points with the option to fill it with the current pattern. If draw centered is set to true, the first point will act as the center of the circle and the second point will be the outer radius edge of it. If the draw center is false, the circle will be drawn to fit inside the boundaries of the 2 points.</td>
  </tr>
  <tr>
    <td>DrawEllipse( x0, y0, x1, y1, fill )</td>
    <td>Draws an ellipse between two points with the option to fill it with the current pattern. If draw centered is set to true, the first point will act as the center of the ellipse and the second point will be the outer radius edge of it. If the draw center is false, the ellipse will be drawn to fit inside the boundaries of the 2 points.</td>
  </tr>
  <tr>
    <td>DrawLine( x0, y0, x1, y1 )</td>
    <td>Draws a line between two points.</td>
  </tr>
  <tr>
    <td>DrawPixels( x, y, drawMode, scale, maskColor, maskColorID )</td>
    <td>Draws the contents of the canvas to a layer. You can also set a scale value, the default is 1, to enlarge the image before rendering it. By default, the canvas is drawn to the tilemap cache layer.</td>
  </tr>
  <tr>
    <td>DrawSprite( id, x, y, flipH, flipV, colorOffset )</td>
    <td>Draws a sprite to the canvas.</td>
  </tr>
  <tr>
    <td>DrawSprites( ids, x, y, width, flipH, flipV, colorOffset )</td>
    <td>Draws an array of sprite IDs to the canvas in a grid.</td>
  </tr>
  <tr>
    <td>DrawSquare( x0, y0, x1, y1, fil )</td>
    <td>Draws a square between two points with the option to fill it with the current pattern.</td>
  </tr>
  <tr>
    <td>DrawText( text, x, y, font, colorOffset, spacing )</td>
    <td>Draw text to the canvas.</td>
  </tr>
  <tr>
    <td>FloodFill( x, y)</td>
    <td>Attempts to perform a flood fill at a point on the canvas. The color at the x,y position of the flood fill will be used as the source color to replace until it runs out of connecting colors. This is a very expensive API so try to avoid using it in large or complex areas.</td>
  </tr>
  <tr>
    <td>LinePattern( x, y )</td>
    <td>Changes the spacing between the X and Y pixel of the line. By default, the X value is set to 1.</td>
  </tr>
  <tr>
    <td>ReadPixelAt( x, y)</td>
    <td>Reads a pixel at a given position and return the color ID.</td>
  </tr>
  <tr>
    <td>SamplePixels( x, y, width, height)</td>
    <td>Returns the pixels, as an array of color ID integers, within the supplied boundaries.</td>
  </tr>
  <tr>
    <td>SetPattern( pixels, width, height )</td>
    <td>Changes the fill pattern for shapes such as the circle, square, and ellipses. The fill pattern is also used by FloodFill().</td>
  </tr>
  <tr>
    <td>SetStroke( pixels, width, height )</td>
    <td>Changes the stroke color and size. It accepts an array of integers. The width x height needs to equal the number of pixels in the array.</td>
  </tr>
  <tr>
    <td>SetStrokePixel( x, y )</td>
    <td>Draws a single stroke pixel. This is used by all of the drawing APIs to create an outline along with a given set of coordinates.</td>
  </tr>
</table>


## Example

In this example, we are going to look at how to draw a line, a circle, and a square including how to fill them with solid colors or patterns:

    class NewCanvasExample : GameChip
    {
        // Store a reference to the canvas here
        private Canvas canvas;

        // This will be our solid pattern value
        private int[] solidPattern = {5};

        // This will be our checkered pattern value
        private int[] checkeredPattern =
        {
            5, 0, 5, 0,
            0, 5, 0, 5,
            5, 0, 5, 0,
            0, 5, 0, 5
        };

        public override void Init()
        { 
            // Create a new canvas the size of the display
            canvas = NewCanvas(Display().X, Display().Y);

            // Set the canvas stroke to a 1x1 pixel brush
            canvas.SetStroke(new int[]{ 6}, 1, 1);

            // Draw the line label to the canvas
            canvas.DrawText("Line", 8, 8, "large", 15);

            // Draw a line between the two points
            canvas.DrawLine(8, 24, 80, 32);

            // Change the spacing between the line's x pixels to 2 for a dotted line
            canvas.LinePattern(2, 0);

            // Draw a line between the two points
            canvas.DrawLine(93, 24, 165, 32);

            // Reset the space between the line's pixels back to 1
            canvas.LinePattern(1, 0);

            // Draw the circle label to the canvas
            canvas.DrawText("Circle", 8, 40, "large", 15);

            // Circle 1
            canvas.DrawCircle(8, 80, 64, 80);

            // Circle 2
            canvas.SetPattern(solidPattern, 1, 1);
            canvas.DrawCircle(74, 80, 130, 80, true);

            // Circle 3
            canvas.SetPattern(checkeredPattern, 4, 4);
            canvas.DrawCircle(140, 80, 196, 80, true);

            // Draw the square label to the canvas
            canvas.DrawText("Square", 8, 120, "large", 15);

            // Square 1
            canvas.DrawSquare(8, 136, 64, 192);

            // Square 2
            canvas.SetPattern(solidPattern, 1, 1);
            canvas.DrawSquare(76, 136, 132, 192, true);

            // Square 3
            canvas.SetPattern(checkeredPattern, 4, 4);
            canvas.DrawSquare(142, 136, 198, 192, true);

            // Draw the canvas to the display
            canvas.DrawPixels();

        }

        public override void Draw()
        { 
            // Redraw the display
            RedrawDisplay();
        }

    }

Running this code will output the following:

<p style="text-align:center"><img src="images/NewCanvasOutput_image_0.png" /></p>

