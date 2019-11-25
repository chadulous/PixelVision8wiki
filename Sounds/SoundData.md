# Sound Data

Pixel Vision 8 sound effects are stored in the `sounds.json` file. This file defines all of the available sound effects that your game can playback at runtime. Each sound effect is stored as a 24 value comma-delimited string. Here is a mapping of each sound property.

<table>
  <tr>
    <td>Order</td>
    <td>Property</td>
    <td>Notes</td>
  </tr>
  <tr>
    <td>1</td>
    <td>waveType</td>
    <td>Supports: Square (0), Saw (1), Sine (2), Noise (3), Triangle (4), Sample (5)</td>
  </tr>
  <tr>
    <td>2</td>
    <td>attackTime</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>3</td>
    <td>sustainTime</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>4</td>
    <td>sustainPunch</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>5</td>
    <td>decayTime</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>6</td>
    <td>startFrequency</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>7</td>
    <td>minFrequency</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>8</td>
    <td>slide</td>
    <td>Range -1 to 1</td>
  </tr>
  <tr>
    <td>9</td>
    <td>deltaSlide</td>
    <td>Range -1 to 1</td>
  </tr>
  <tr>
    <td>10</td>
    <td>vibratoDepth</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>11</td>
    <td>vibratoSpeed</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>12</td>
    <td>changeAmount</td>
    <td>Range -1 to 1</td>
  </tr>
  <tr>
    <td>13</td>
    <td>changeSpeed</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>14</td>
    <td>squareDuty</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>15</td>
    <td>dutySweep</td>
    <td>Range -1 to 1</td>
  </tr>
  <tr>
    <td>16</td>
    <td>repeatSpeed</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>17</td>
    <td>phaserOffset</td>
    <td>Range -1 to 1</td>
  </tr>
  <tr>
    <td>18</td>
    <td>phaserSweep</td>
    <td>Range -1 to 1</td>
  </tr>
  <tr>
    <td>19</td>
    <td>lpFilterCutoff</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>20</td>
    <td>lpFilterCutoffSweep</td>
    <td>Range -1 to 1</td>
  </tr>
  <tr>
    <td>21</td>
    <td>lpFilterResonance</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>22</td>
    <td>hpFilterCutoff</td>
    <td>Range 0 to 1</td>
  </tr>
  <tr>
    <td>23</td>
    <td>hpFilterCutoffSweep</td>
    <td>Range -1 to 1</td>
  </tr>
  <tr>
    <td>24</td>
    <td>masterVolume</td>
    <td>Range 0 to 1</td>
  </tr>
</table>


You can use any Sfxr compatible sound generator to create a compatible 24 parameter string file for each sound effect.

Each sound effect is stored inside of the `SoundChip`’s `sounds` array property. Here is an example of how the file is structured:

`{`

  "SoundChip": {

    "sounds": [
      {
        "name": "Melody",
        "settings": "0,.05,,.2,,.2,.3,.1266,,,,,,,,,,,,,,,,,,1,,,,,,"
      }
    ]
  }
`}`

This file will contain the maximum number of sound effects your game can support which is defined in the `data.json` file. You can change this cap by modifying the `totalSounds `property of the `SoundChip`.

Finally, you can configure the sound channels in the data.json file. The SoundChip contains a property called channelType with an array of values that map to each WaveType. 

`"channelTypes": [-1, -1, -1, -1, -1]`

Setting a channel to `-1` will support playing any wave type. If you set it to a specific wave type ID, that channel will override the sound effect’s `waveType `property. Here is an example of how to configure the channels to match up to a NES’s specs:

`"channelTypes":[0,0,4,3,5]`

In this configuration, the `SoundChip` will enforce channels 1 & 2 as `Square`, channel 3 as `Triangle`, channel 4 as `Noise`, and channel 5 as `Sample` which allows you to only play `.wav` files. It’s important to understand the connection between the sound effect data’s `waveTyp`e property and the `SoundChip`’s `channelTypes` to correctly playback each sound effect as expected.


