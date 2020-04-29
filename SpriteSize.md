The `SpriteSize(`) API returns the default sprite size as a read-only `Point` where `X` and `Y` represent the `Width` and `Height`.

## Usage

`SpriteSize ( )`

## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Point</td>
    <td>Returns a Point where the X and Y for the sprite's width and height</td>
  </tr>
</table>


## Example

In this example, we are going to read the `SpriteSize()` API and display it on the screen:

    class SpriteSizeExample : GameChip
    {
        public override void Init()
        {
            // Get the sprite size
            var spriteSize = SpriteSize();

            // Draw the sprite size to the display
            DrawText("Sprite Size: " + spriteSize.X + "x" + spriteSize.Y, 1, 1, DrawMode.Tile, "large", 15);

        }

        public override void Draw()
        { 
            // Redraw the display
            RedrawDisplay();
        }
    }

Running this code will output the following:

![image alt text](images/SpriteSizeOutput_image_0.png)

