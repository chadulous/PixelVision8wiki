# SplitLines()

The `SplitLines()` API converts text with line breaks (`\n`) into an array. This can be used in conjunction with the `WordWrap()` helper to render large blocks of text line by line with the `DrawText()` API.

## Usage

```csharp
SplitLines ( str )
```

## Arguments

| Name | Value  | Description                   |
|------|--------|-------------------------------|
| str  | string | The string of text to split\. |

## Returns

| Value      | Description                                                  |
|------------|--------------------------------------------------------------|
| string\[\] | Returns an array of strings representing each line of text\. |

## Example

In this example, we are going to use the `SplitLines()` API to create an array of text to draw to the display:



## Lua

```lua
-- Message to display on the screen
local message = "PIXEL VISION 8\n\n\nVisit 'pixelvision8.com' to learn more about creating games from scratch."

function Init()

  -- To convert the message into lines of text we need to wrap it then split it
  local wrap = WordWrap(message, (Display().x / 8) - 2)
  local lines = SplitLines(wrap)

  -- Loop through each line of text and draw it to the display
  for i = 1, #lines do
    DrawText(lines[i], 1, i, DrawMode.Tile, "large", 15)
  end

end

function Draw()
  -- Redraw the display
  RedrawDisplay()
end
```



## C#

```csharp
class SplitLinesExample : GameChip
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
            DrawText(lines[i], 1, i+1, DrawMode.Tile, "large", 15);
        }

    }

    public override void Draw()
    { 
        // Redraw the display
        RedrawDisplay();
    }
}
```



Running this code will output the following:

![image alt text](images/SplitLinesOutput_image_0.png)


