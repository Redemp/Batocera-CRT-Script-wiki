# Under Contruction


The script will create the file `es.arg.override` in the folder
`/userdata/system`

![screensizeoffset](https://github.com/ZFEbHVUE/Batocera-CRT-Script/blob/main/wiki_page/scaling_crt.png)

`screensizeoffset_x = width`

`screensizeoffset_y= height`

Top-left is the anchor, increasing will stretch the image out to the right and downwards; decreasing will squash the image from the right side toward the left and from the bottom upwards.

`screensizeoffset_x 00`

`screensizeoffset_y 00`


![screenoffset](https://github.com/ZFEbHVUE/Batocera-CRT-Script/blob/main/wiki_page/offset_crt.png)

We will start by aligning the top-left of the image with the top-left corner of the display. This will be important for the next step (scaling). We will do this by utilizing the following argument: 
Move the canvas by [x] pixels right and [y] pixels down.

`screenoffset_x 00`

`screenoffset_y 00`

If your resolution is `640 480` and you put for example

`screensizeoffset_x 10`

`screensizeoffset_y -10`

`screenoffset_x -5`

`screenoffset_y 5`

you will get :

`es.customsargs=--screensize 650 470 --screenoffset -5 5`

so you can adjust your screen by using this file   es.arg.override (edited)

And each time your re-use the script.  the file `/userdata/system/es.arg.override` will be erased so make a backup.


You must put the offset not the resolution into /userdata/system/es.arg.override
