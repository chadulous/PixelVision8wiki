# StopSound()

Use `StopSound()` to stop any sound playing on a specific channel.

## Usage

```csharp
StopSound ( channel )
```

## Arguments

| Name    | Value | Description                         |
|---------|-------|-------------------------------------|
| channel | int   | The channel ID to stop a sound on\. |

## Example

In this example, we toggle between playing and stopping a sound effect based on the mouse button being released:



## Lua

```lua
-- Store the playback state of channel 0
local isPlaying = false

function Update(timeDelta)

  -- See if the channel has audio playing back on it
  isPlaying = IsChannelPlaying(0)

  -- Test if the left mouse button was released and if isPlaying equals false
  if(MouseButton(0, InputState.Released)) then

    -- Check to see if the channel is playing a sound
    if(isPlaying) then

      -- Stop the sound
      StopSound(0)

    else
      -- Play the second sound effect
      PlaySound(1)

    end
  end
end

function Draw()

  -- Redraw display
  RedrawDisplay()

  -- Test to see if the sound effect is playing
  if(isPlaying) then

    -- Draw the sound playback label
    DrawText("Click To Stop Sound Effect", 8, 8, DrawMode.Sprite, "large", 14)

  else

    -- Draw the instructions label
    DrawText("Click To Play Sound Effect", 8, 8, DrawMode.Sprite, "large", 15)

  end
end
```



## C#

```lua
class StopSongExample : GameChip
{
    public override void Init()
    { 
        // Draw the song data label
        DrawText("Song Data:", 1, 1, DrawMode.Tile, "large", 15);

    // Start playing the song on a loop
    PlaySong(0, true);

    }

    public override void Update(int timeDelta)
    { 

        // Test for the left mouse button to be released
        if(MouseButton(0, InputState.Released))
        { 

            // Stop the song when the mouse button is released
            StopSong();

        }

    }

    public override void Draw()
    { 

        // Redraw display
        RedrawDisplay();

        // Reset the next row value so we know where to draw the first line of text
        var nextRow = 2;

        // Display the song's metadata
        foreach (var data in SongData())
        {

            //Draw the key value pair from the song data table
            DrawText(data.Key + ":", 8, nextRow * 8, DrawMode.Sprite, "large", 6);
            DrawText(data.Value.ToString(), 16 + (data.Key.Length * 8), nextRow * 8, DrawMode.Sprite, "large", 14);

            //Increment the row by 1 for the next loop

            nextRow = nextRow + 1;

        }
    }
}
```



Running this code will output the following:

![image alt text](images/StopSoundOutput_image_0.png)


