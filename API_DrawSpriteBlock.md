# DrawSpriteBlock

The `DrawSpriteBlock()` API allows you to draw multiple sprites to the screen in a single call. This works similar to `DrawSprite(),` except you define the first sprite (upper left corner) then the `width `and `height `(in sprites) to sample from `SpriteChip`’s memory. For example, if you passed in an ID of 0 which is the first sprite, then a  `width `and `height `of `2` the `DrawSpriteBlock()` API would combine all 4 sprites into a single draw call.

<p style="text-align:center"><img src="images/DrawSpriteBlock_image_0.png" /></p>

The `DrawSpriteBlock()` API also supports flipping the sprite and color offsets like `DrawSprite()` but adds some additional arguments to help make it easier to work with multiple sprites as a single sprite.

The first argument, `onScreen`, determines what should happen to the sprites when they go off-screen. The second argument, `useScrollPos`, will apply the current scroll position value to the sprite’s `X` and `Y` values for you. And the final argument, `bounds`, allows you to define a custom rectangle that acts similar to a mask.

## Usage

`DrawSpriteBlock ( id, x, y, width, height, flipH, flipV, drawMode, colorOffset, onScreen, useScrollPos, bounds )`

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
    <td>The top left sprite to start with.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>An int value representing the X position to place the sprites on the display. If set to 0, it renders on the far left-hand side of the screen.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An int value representing the Y position to place sprite on the display. If set to 0, it renders on the top of the screen.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td>The width, in sprites, of the grid. A value of 2 renders 2 sprites wide.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>int</td>
    <td>The height, in sprites, of the grid. A value of 2 renders 2 sprites height.</td>
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
  <tr>
    <td>onScreen</td>
    <td>bool</td>
    <td>This flag defines if the sprites should not render when they are off the screen. Use this in conjunction with overscan border control what happens to sprites at the edge of the display. If this value is false, the sprites wrap around the screen when they reach the edges of the screen.</td>
  </tr>
  <tr>
    <td>useScrollPos</td>
    <td>bool</td>
    <td>This will automatically offset the sprite's x and y position based on the scroll value.</td>
  </tr>
  <tr>
    <td>bounds</td>
    <td>Rectangle</td>
    <td>A custom mask to constrain the sprite. Moving the sprites outside of the rectangle will hide them when onScreen is set to false.</td>
  </tr>
</table>


## Draw Modes

The `DrawSpriteBlock()` API supports the following draw modes:

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

For this example, we are going to render two blocks of sprites to the display. The first group will hide when their `X` value goes past the screen and the second group will wrap when their Y value is offscreen similar to using the `DrawSprite()` API. To do this, we need the first sprite’s ID which you can find by using Pixel Vision OS’s Sprite Tool.

<p style="text-align:center"><img src="images/DrawSpriteBlock_image_1.png" /></p>

To help get an idea of what the sprite will look like, we can use the Sprite Tool’s size button to increase or decrease the sprites displayed on the canvas. To calculate a sprite’s ID by hand, you can find the first sprite at the top left part of the `sprites.png` file. Once we have the sprite’s ID we can use the following code example to draw it:

    class DrawSpriteBlock : GameChip
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

            // Draw sprite block moving horizontally and hide when it goes offscreen
            DrawSpriteBlock(168, pos.X, 8, 2, 2);

            // Draw flipped sprite block moving vertically but render when offscreen
            DrawSpriteBlock(168, 36, pos.Y, 2, 2, true, false, DrawMode.Sprite, 0, false);

            // Draw the x,y position of each sprite
            DrawText("(" + MathUtil.FloorToInt(nextPos) + ",8)", pos.X + 20, 8, DrawMode.Sprite, "large", 15);
            DrawText("(36," + MathUtil.FloorToInt(nextPos) + ")", 56, pos.Y, DrawMode.Sprite, "large", 15);

        }
    }

Running this code will output the following:

<p style="text-align:center"><img src="images/DrawSpriteBlockOutput_image_0.png" /></p>

When the horizontal sprite moves past the boundary of the screen, it will stop rendering even though the `X` value continues to increase. 

<p style="text-align:center"><img src="images/DrawSpriteBlockOutput_image_1.png" /></p>

