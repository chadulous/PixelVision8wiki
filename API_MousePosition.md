# MousePosition

The `MousePosition()` API returns a Point for the mouse cursor's `X` and `Y` position. The mouse's `0`,`0` position is in the upper left-hand corner of the display and when the mouse is off-screen it will return `-1`. This value is read-only. 

## Usage

`MousePosition ( )`

## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>bool</td>
    <td>Returns a point representing the mouse’s x,y position on the screen.</td>
  </tr>
</table>


## Example

In this example, we will display the mouse position and draw an 8 x 8 pixel rectangle to display it on the screen:

    class MousePositionExample : GameChip
    {
        
        // Store the current position of the mouse
        private Point pos;

        public override void Init()
        { 
            // Draw the text for where the position will be displayed
            DrawText("Mouse Position", 1, 1, DrawMode.Tile, "large", 15);

        }

        public override void Update(int timeDelta)
        { 
            // Update the mouse position
            pos = MousePosition();

        }

        public override void Draw()
        { 
            // Redraw the display
            RedrawDisplay();

            // Test if the mouse is offscreen first
            if (pos.X == -1 || pos.Y == -1)
            {

                // Display that the mouse is offscreen
                DrawText("Offscreen", 128, 8, DrawMode.Sprite, "large", 14);

            } else { 

                // Draw a rectangle that follows the mouse on the screen
                DrawRect(pos.X, pos.Y, 8, 8, 5);

                // Display the X and Y position of the mouse
                DrawText(pos.X + "," + pos.Y, 128, 8, DrawMode.Sprite, "large", 14);

            }
        }
    }

Running this code will output the following:

<p style="text-align:center"><img src="images/MousePositionOutput_image_0.png" /></p>

