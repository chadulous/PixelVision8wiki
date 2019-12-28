# DrawSprite

The DrawSprite() API allows you to draw a single sprite to the display. Sprites represent individual collections of 8 x 8 blocks of pixel data. Each sprite is cached by the `SpriteChip `making sprite draw requests very fast. The display also has a limitation on how many sprites that can be on the screen at the same time. Each time you call `DrawSprite()`, the sprite counts against the total amount the display can render. If you attempt to draw more sprites than the display can handle, the call is ignored. One thing to keep in mind when drawing sprites is that their `X` and `Y` positions wrap if they reach the right or bottom border of the screen. You can use the display’s overscan to hide sprites offscreen until they are needed.

Using the `DrawSprite()` API also allows you to flip the pixel data horizontally or vertically as well as change the color ID values. To conserve the `SpriteChip`’s memory, you can use these three pre-render flags to optimize your sprites.

## Usage

`DrawSprite ( id, x, y, flipH, flipV, drawMode, colorOffset )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td>The unique ID of the sprite to use in the SpriteChip.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>An int value representing the X position to place sprite on the display. If set to 0, it renders on the far left-hand side of the screen.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An int value representing the Y position to place the sprite on the display. If set to 0, it renders on the top of the screen.</td>
  </tr>
  <tr>
    <td>flipH</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool. The default value is set to false but passing in true flips the pixel data horizontally.</td>
  </tr>
  <tr>
    <td>flipV</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool. The default value is set to false but passing in true flips the pixel data vertically.</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td>This argument accepts the DrawMode enum. You can use Sprite, SpriteBelow, and TilemapCache to change where the pixel data is drawn to. By default, this value is DrawMode.Sprite.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>This optional argument accepts an int that offsets all the color IDs in the pixel data array. This value is added to each int, in the pixel data array, allowing you to simulate palette shifting.</td>
  </tr>
</table>


## Draw Modes

The `DrawSprite()` API supports the following draw modes:

<table>
  <tr>
    <td>DrawMode</td>
    <td>Layer ID</td>
    <td>Supported</td>
  </tr>
  <tr>
    <td>TilemapCache</td>
    <td>-1</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Background</td>
    <td>0</td>
    <td>No</td>
  </tr>
  <tr>
    <td>SpriteBelow</td>
    <td>1</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Tile</td>
    <td>2</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Sprite</td>
    <td>3</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>UI</td>
    <td>4</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>SpriteAbove</td>
    <td>5</td>
    <td>Yes</td>
  </tr>
</table>


Attempting to use an unsupported draw mode will cancel the draw request. When using `DrawMode.TilemapCache` or `DrawMode.Tile`, the tilemap’s coordinate space will be used. In the case of `DrawMode.Tile`, the `X` and `Y` values will become `Column` and `Row`. For `DrawMode.TilemapCache` you can use `X` and `Y` to place the sprite on the tilemap itself. That means that wrapping for the sprite’s coordinates will switch from the screen boundaries to the tilemap itself.

## Example

For this example, we are going to render a sprite to the display. To do this, we need the sprite’s ID which you can find in Pixel Vision OS’s Sprite Tool.

<p style="text-align:center"><img src="images/DrawSprite_image_0.png" /></p>

To calculate a sprite’s ID by hand, you can find the first sprite at the top left part of the `sprites.png` file. Once we have the sprite’s ID we can use the following code example to draw it:

    class DrawSprite : GameChip
    {
        // Use floats to store the subpixel position
        private float speed = 5;
        private float nextPos;

        // Use this point to position the  sprites
        private Point pos;

        public override void Update(int timeDelta)
        { 
            // Calculate the next position
            nextPos = nextPos + (speed * (timeDelta / 100f));

            // Need to convert the nextPoint to an int, so we'll save it in a point
            pos.X = (int)nextPos;
            pos.Y = (int)nextPos;
        }

        public override void Draw()
        { 
            // Redraw the display
            RedrawDisplay();

            // Draw sprite moving horizontally
            DrawSprite(376, pos.X, 8);

            // Draw sprite moving vertically
            DrawSprite(377, 36, pos.Y);

            // Draw the x,y position of each sprite
            DrawText("("+MathUtil.FloorToInt(nextPos)+",8)", pos.X + 8, 8, DrawMode.Sprite, "large", 15);
            DrawText("(36,"+ MathUtil.FloorToInt(nextPos)+")", 44, pos.Y, DrawMode.Sprite, "large", 15);

        }
    }

Running this code will output the following:

<p style="text-align:center"><img src="images/DrawSpriteOutput_image_0.png" /></p>

