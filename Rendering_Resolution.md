# Resolution

Each game can have its own resolution define which is defined in the game’s `data.json` file. There are 4 properties that help make up a game’s final resolution. These properties have their own minimum and maximum values which help ensure that Pixel Vision 8’s renderer is able to correctly draw to the screen without impacting performance. Here is a list of the `DisplayChip`’s properties and value range.

<table>
  <tr>
    <td>DisplayChip Property</td>
    <td>Minimum Value</td>
    <td>Maximum Value</td>
  </tr>
  <tr>
    <td>width</td>
    <td>64</td>
    <td>512</td>
  </tr>
  <tr>
    <td>height</td>
    <td>64</td>
    <td>480</td>
  </tr>
  <tr>
    <td>overscanX</td>
    <td>0</td>
    <td>4</td>
  </tr>
  <tr>
    <td>overscanY</td>
    <td>0</td>
    <td>4</td>
  </tr>
</table>


Keep in mind that a game’s resolution will not affect the screen’s resolution. The game is automatically upscaled to fill the screen.

While it’s possible to have resolutions larger than 256 x 240, there may be a performance penalty. At Pixel Vision 8’s default resolution of 256 x 240 pixels, the display will render 61,440 pixels per frame. Larger resolutions increase this number exponentially and drastically slow down rendering. If you are having issues with a game running on lower-powered systems, it is best to use a smaller resolution. The fewer pixels you attempt to render, the better the performance.

