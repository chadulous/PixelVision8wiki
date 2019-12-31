While you can arrange your `.font.png` character sprites in any grid-based layout, the order of the characters is important. To allow the FontChip to correctly map each character to it’s ASCII equivalent, it is best practice to follow this template:

<p style="text-align:center"><img src="images/FontTemplate_image_0.png" /></p>

While the default template only supports the standard English character set, special characters can also be added. They will be parsed and assigned an ASCII ID exactly like the main set of characters.

Finally, any characters that match or are empty will be optimized by the importer. So you can ignore some character sets, such as lowercase if you need to save memory. Simply leave those characters empty in the font file.

