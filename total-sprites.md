# TotalSprites()

The `TotalSprites()` API returns the total number of sprites in the `SpriteChip`. By supplying `true `for the `ignoreEmpty `parameter, it will only return sprites that contain pixel data. If all of the values of a sprite’s pixel data are set to `-1`, it will be considered empty by the `SpriteChip`.

## Usage

```csharp
TotalSprites ( ignoreEmpty )
```

## Arguments

| Name        | Value | Description                                                                                                                                                                              |
|-------------|-------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ignoreEmpty | bool  | This is an optional parameter that defaults to false to get all available sprites from the SpriteChip or supply true for non\-empty \(where all the pixel data is set to \-1\) sprites\. |

## Returns

| Value | Description                                                                                                   |
|-------|---------------------------------------------------------------------------------------------------------------|
| int   | This method returns the total number of sprites in the color chip based on the ignoreEmpty argument's value\. |

## Example

In this example, we are going to display the total sprite values:



## Lua

```lua
function Init()

  -- Get total colors values
  local totalSprites = TotalSprites()
  local usedSprites = TotalSprites(true)

  -- Display the used vs total colors on the screen
  DrawText("Total Sprites " .. usedSprites .. "/" .. totalSprites, 1, 1, DrawMode.Tile, "large", 15)

end

function Draw()
  -- Redraw the display
  RedrawDisplay()
end
```



## C#

```csharp
class TotalSpritesExample : GameChip
{
    public override void Init()
    {
        // Get total colors values
        var totalSprites = TotalSprites();
        var usedSprites = TotalSprites(true);

        // Display the used vs total colors on the screen
        DrawText("Total Sprites " + usedSprites + "/" + totalSprites, 1, 1, DrawMode.Tile, "large", 15);

    }

    public override void Draw()
    {
        // Redraw the display
        RedrawDisplay();
    }
}
```



Running this code will output the following:

![image alt text](images/TotalSpritesOutput_image_0.png)


