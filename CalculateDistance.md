# CalculateDistance

A fast way to calculate the distance between two points.

## Usage

`CalculateDistance ( x0, y0, x1, y1 )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>x0</td>
    <td>int</td>
    <td>The first point’s x position.</td>
  </tr>
  <tr>
    <td>y0</td>
    <td>int</td>
    <td>The first point’s y position.</td>
  </tr>
  <tr>
    <td>x1</td>
    <td>int</td>
    <td>The second point’s x position.</td>
  </tr>
  <tr>
    <td>y1</td>
    <td>int</td>
    <td>The second point’s y position.</td>
  </tr>
</table>


## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>int</td>
    <td>Returns an integer for the distance between the two points.</td>
  </tr>
</table>


## Example

In this example, we will calculate the distance between 2 points and use a canvas to visualize it:

    class CalculateDistanceExample : GameChip
    {
        private Point pointA = new Point(8, 8);
        private Point pointB = new Point(248, 232);
        private Canvas canvas;
        private int distance;

        public override void Init()
        {

            // Create a new canvas and pass this GameChip into the constructor
            canvas = new Canvas(256, 240, this);

            // Set the canvas stroke to a white 1x1 pixel brush
            canvas.SetStroke(new []{15}, 1, 1);

        }

        public override void Update(int timeDelta)
        { 

            // Update position B with the MousePosition
            pointB = MousePosition();

            // Calculate the distance between pointA and pointB
            distance = CalculateDistance(pointA.X, pointA.Y, pointB.X, pointB.X);

        }

        public override void Draw()
        {

            // Redraw the display
            RedrawDisplay();

            // Clear the canvas with the background color
            canvas.Clear(0);

            // Draw 2 circles around each point
            canvas.DrawCircle(pointA.X - 4, pointA.Y - 4, pointA.X + 4, pointA.Y + 4);
            canvas.DrawCircle(pointB.X - 4, pointB.Y - 4, pointB.X + 4, pointB.Y + 4);

            // Draw a line between the two points
            canvas.DrawLine(pointA.X, pointA.Y, pointB.X, pointB.Y);

            // Draw the distance value above pointB
            canvas.DrawText(distance.ToString(), pointB.X, pointB.Y - 12, "small", 15, -4);

            // Draw the canvas to the display
            canvas.DrawPixels();

        }
    }

Running this code will output the following:

<p style="text-align:center"><img src="images/CalculateDistanceOutput_image_0.png" /></p>

