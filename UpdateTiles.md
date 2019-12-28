# UpdateTiles

The `UpdateTiles()` API allows you to update the color offset and flag values of multiple tiles at once. Simply supply an array of tile IDs and the new tile’s color offset and a flag value. This helper method uses the `Tile()` API under the hood to update each tile, so any changes to a tile’s color offset will automatically force it to be redrawn to the tilemap cache layer. Use this when you don’t need to make changes to each tile’s sprite ID and don’t want to manually iterate over large collections of tiles manually.

## Usage

`UpdateTiles ( ids, column, row, width, colorOffset, flag )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>ids</td>
    <td>int[]</td>
    <td>An array of sprite IDs to use for each tile being updated.</td>
  </tr>
  <tr>
    <td>column</td>
    <td>int</td>
    <td>Start column of the first tile to update. The 0 column is on the far left of the tilemap.</td>
  </tr>
  <tr>
    <td>row</td>
    <td>int</td>
    <td>Start row of the first tile to update. The 0 row is on the top of the tilemap.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>An optional color offset int value to be applied to each updated tile.</td>
  </tr>
  <tr>
    <td>flag</td>
    <td>int</td>
    <td>An optional flag int value to be applied to each updated tile.</td>
  </tr>
</table>


## Example

In this example, we are going to read all of the tiles and see which ones have sprites assigned to them. We’ll be using the following Tilemap:

<p style="text-align:center"><img src="images/UpdateTiles_image_0.png" /></p>

Next, we’ll set up 4 palettes to apply to each of these tiles:

<p style="text-align:center"><img src="images/UpdateTiles_image_1.png" /></p>

<p style="text-align:center"><img src="images/UpdateTiles_image_2.png" /></p>

<p style="text-align:center"><img src="images/UpdateTiles_image_3.png" /></p>

<p style="text-align:center"><img src="images/UpdateTiles_image_4.png" /></p>

Finally, we’ll change each tile’s `colorOffset` value over several frames to give the impression that the background is fading up and down:

    class UpdateTilesExample : GameChip
    {
        // Set up a time and delay
        private int time;
        private int delay = 800;

        // This will be the direction value for the transition
        private int dir = 1;

        // Total number of palettes for transition
        private int max = 3;

        // Current palette ID
        private int paletteID;

        // Store the tilemap dimensions
        private Point mapSize;
        private int totalTiles;

        // Store all of the tiles that should be updated
        int[] tileIDs;

        public override void Init()
        {

            // Set the tilemap dimensions
            mapSize = TilemapSize();
            totalTiles = mapSize.X * mapSize.Y;

            // We'll use a list to store tile IDs
            var tileList = new List&lt;int&gt;();

            // Loop through all of the tiles in the tilemap
            for (int i = 0; i &lt; totalTiles; i++)
            {
           
                // Convert the loop index to a column,row position
                var pos = CalculatePosition(i, mapSize.X);

                // Check to see if the tile has a sprite
                if (Tile(pos.X, pos.Y).spriteID &gt; -1)
                {
                    tileList.Add(i);

                }
            }

            // Convert the tileList into an array
            tileIDs = tileList.ToArray();
        }

        public override void Update(int timeDelta)
        {
            // Increase the time on each frame and test if it is greater than the delay
            time = time + timeDelta;

            if (time &gt; delay)
            {

                // Update the palette ID based on the direction
                paletteID += dir;

                // Test if the palette ID is too small or too large and reverse the direction
                if (paletteID &gt;= max)
                {
                    dir = -1;
                }
                else if (paletteID &lt;= 0)
                {
                    dir = 1;
                }

                // Reset the time value
                time = 0;

                // Update each tile's color offset
                UpdateTiles(tileIDs, PaletteOffset(paletteID));
            }
        }

        public override void Draw()
        {
            // Redraw the display
            RedrawDisplay();

            // Draw the text for the palette and color ID
            DrawText("Palette " + paletteID, 32, 16, DrawMode.Sprite, "large", 15);

        }
    }

One thing to note is that while this demo shows how to modify individual tiles at run-time, it’s important to point out that this approach may have bad performance impacts. If you need to modify large groups of tiles, try indexing them in the tilemap during startup and only iterate over tiles you know you need to update.

Running this code will output the following:

<p style="text-align:center"><img src="images/UpdateTilesOutput_image_0.png" /></p>

