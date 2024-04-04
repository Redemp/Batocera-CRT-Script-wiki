# Under Contruction


The script will create the file `es.arg.override` in the folder
`/userdata/system`

The file will will contain these vales
* screensizeoffset_x 0
* screensizeoffset_y 0
* screenoffset_x 0
* screenoffset_y 0 

# Offset -> Position

<img src="https://github.com/ZFEbHVUE/Batocera-CRT-Script/blob/main/wiki_page/offset_crt.png" width=50% height=50%>

Lets start with the Offset

We will start by aligning the top-left of the image with the top-left corner of the display. This will be important for the next step (Scaling -> Size). We will do this by utilizing the following argument: 
Move the canvas by [x] pixels right and [y] pixels down.

`screenoffset_x 00`

`screenoffset_y 00`



# Scaling -> Size
<img src="https://github.com/ZFEbHVUE/Batocera-CRT-Script/blob/main/wiki_page/scaling_crt.png" width=50% height=50%>

Top-left is the anchor, increasing will stretch the image out to the right and downwards; decreasing will squash the image from the right side toward the left and from the bottom upwards.

`screensizeoffset_x = width`

`screensizeoffset_y= height`

`screensizeoffset_x 00`

`screensizeoffset_y 00`

# Example 

If your resolution is `640 480` and you put for example

`screensizeoffset_x 10`

`screensizeoffset_y -10`

`screenoffset_x -5`

`screenoffset_y 5`

you will get :

`es.customsargs=--screensize 650 470 --screenoffset -5 5`


And each time your re-use the script.  the file `/userdata/system/es.arg.override` will be erased so make a backup.
