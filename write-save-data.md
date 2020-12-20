# WriteSaveData()

The `WriteSaveData()` API allows you to write saved data by supplying a key and value. Once saved, this data persists even after restarting a game.

## Usage

```csharp
WriteSaveData( key, value )
```

## Arguments

| Name  | Value  | Description                                  |
|-------|--------|----------------------------------------------|
| key   | string | A string to use as the key for the data\.    |
| value | string | A string representing the data to be saved\. |

## Example

In this example, we are going to attempt to read the last time the game was loaded. When the game shuts down, it will save a timestamp to be read the next time the game is run:

## Lua

```lua
function Init()

  -- Draw the last opneded text
  DrawText("Last Opened", 1, 1, DrawMode.Tile, "large", 15)

  -- Draw the saved data to the display
  DrawText(ReadSaveData("LastOpened", "Never"), 1, 2, DrawMode.Tile, "large", 14)

end

function Draw()
  -- Redraw the display
  RedrawDisplay()
end

-- When the game shuts down, it will automatically save the timestamp
function Shutdown()

  -- Write timestamp to the saves.json file.
  WriteSaveData("LastOpened", os.date('%Y-%m-%d %H:%M:%S', ts))
  
end
```



## C#

```csharp
class WriteSaveDataExample : GameChip
{
    public override void Init()
    {
        // Draw the last opneded text
        DrawText("Last Opened", 1, 1, DrawMode.Tile, "large", 15);

        // Draw the saved data to the display
        DrawText(ReadSaveData("LastOpened", "Never"), 1, 2, DrawMode.Tile, "large", 14);

    }

    public override void Draw()
    {
        // Redraw the display
        RedrawDisplay();
    }

    // When the game shuts down, it will automatically save the timestamp
    public override void Shutdown()
    {
        // Write timestamp to the saves.json file.
        WriteSaveData("LastOpened", DateTime.Now.ToString());

        //  TODO need a utility to write this to the file system since it's not run in the main engine

    }
}
```



Running this code will output the following:

![image alt text](images/WriteSaveDataOutput_image_0.png)


