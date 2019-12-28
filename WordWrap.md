The `WordWrap()` API allows you to wrap a string of text to a specified character width. It will automatically insert new line breaks (`\n`) to keep each line of text within the specified width. This can be used in conjunction with the `SplitLines()` API to render large blocks of text to the display line by line within a specific character width.

## Usage

`WordWrap ( text, width )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>text</td>
    <td>string</td>
    <td>The string of text to wrap.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td>The width of characters to wrap each line of text.</td>
  </tr>
</table>


## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>string</td>
    <td>Returns a string of text back with new line breaks as the specified character width.</td>
  </tr>
</table>


## Example

In this example, we are going to use the `WordWrap()` API to create an array of text to draw to the display:

    class WordWrapExample : GameChip
    {

        // Message to display on the screen
        private string message = "PIXEL VISION 8\n\n\nVisit 'pixelvision8.com' to learn more about creating games from scratch.";

        public override void Init()
        {

            // To convert the message into lines of text we need to wrap it then split it
            var wrap = WordWrap(message, (Display().X / 8) - 2);
            var lines = SplitLines(wrap);

            // Loop through each line of text and draw it to the display
            for (int i = 0; i &lt; lines.Length; i++)
            {
                DrawText(lines[i], 1, i + 1, DrawMode.Tile, "large", 15);
            }

        }

        public override void Draw()
        {
            // Redraw the display
            RedrawDisplay();
        }
    }

Running this code will output the following:

<p style="text-align:center"><img src="images/WordWrapOutput_image_0.png" /></p>

