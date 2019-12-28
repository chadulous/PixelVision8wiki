# PlaySound

The `PlaySound()` API allows playing a single sound effect on a specific channel. The `SoundChip `has a limited number of active channels, so playing a sound effect on a channel where a sound is already playing will override it. Since the `MusicChip` shares the same audio channels, playing sound effects while a song is playing on a channel will temporarily stop the song playing on that channel and play the sound effect until the next note of the song is triggered which will overwrite the sound effect. 

Finally, each audio channel can be locked to play a single wave type which will override the sound effect’s own wave channel which alters what the effect will sound like. Before playing a sound, you’ll want to make sure you are using an audio channel that supports its wave type. 

## Usage

`PlaySound ( int id, int channel )`

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
    <td>The ID of the sound in the SoundChip.</td>
  </tr>
  <tr>
    <td>channel</td>
    <td>int</td>
    <td>An optional audio channel ID to play the sound on. Channel 0 is set by default.</td>
  </tr>
</table>


## Example

In this example, we’ll play a sound effect on channel 0 when the mouse is pressed:

    class PlaySoundExample : GameChip
    {
        
        // Store the playback state of channel 0
        private bool isPlaying = false;

        public override void Update(int timeDelta)
        { 
            // See if the channel has audio playing back on it
            isPlaying = IsChannelPlaying(0);

            // Test if the left mouse button was released and if isPlaying equals false
            if(MouseButton(0, InputState.Released) && isPlaying == false) 
            {

                // Play the second sound effect
                PlaySound(1);

            }
        }

        public override void Draw()
        { 

            // Redraw display
            RedrawDisplay();

            // Test to see if the sound effect is playing
            if (isPlaying)
            {

                // Draw the sound playback label
                DrawText("Playing On Channel 0", 8, 8, DrawMode.Sprite, "large", 14);

            } else { 

                // Draw the instructions label
                DrawText("Click To Play Sound Effect", 8, 8, DrawMode.Sprite, "large", 15);

            }
        }
    }

Running this code will output the following:

<p style="text-align:center"><img src="images/PlaySoundOutput_image_0.png" /></p>

