# PlaySound ( int id, int channel )

This method plays back a sound on a specific channel. The SoundChip has a limit of active channels so playing a sound effect while another was is playing on the same channel will cancel it out and replace with the new sound.

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
    <td>The ID of the sound in the SoundCollection.</td>
  </tr>
  <tr>
    <td>channel</td>
    <td>int</td>
    <td>The channel the sound should play back on. Channel 0 is set by default.</td>
  </tr>
</table>


