# Overview

This guide describes manual scaling and centering for cases in which these
operations within the service menu and CRT geometry tool do not produce
a perfectly centered screen.

Manual adjustments can be configured using the file /userdata/system/es.arg.override
which must be edited at the command line.


# es.arg.override

Executing the CRT script will create the file `es.arg.override` in the folder
`/userdata/system`

The file will initially contain the following values
* screensizeoffset_x 0
* screensizeoffset_y 0
* screenoffset_x 0
* screenoffset_y 0 

This file can be edited at the command line (via SSH) using nano or equivalent
editor.

Every time you make a change you need to restart Emulation Station using
`batocera-es-swissknife --restart`

# Offset -> Position

<img src="https://github.com/ZFEbHVUE/Batocera-CRT-Script/blob/main/wiki_page/offset_crt.png" width=50% height=50%>

Let's start with the Offset

We will start by aligning the top-left of the image with the top-left corner of the display. This will be important for the next step (Scaling -> Size). We will do this by utilizing the following argument: 


* screenoffset_x = Horizontal Position
* screenoffset_y = Vertical Position

`screenoffset_x 00`

`screenoffset_y 00`

Move the canvas by [x] pixels right offset and [y] pixels down offset.

# Scaling -> Size
<img src="https://github.com/ZFEbHVUE/Batocera-CRT-Script/blob/main/wiki_page/scaling_crt.png" width=50% height=50%>

Top-left is the anchor, increasing will stretch the image out to the right and downwards; decreasing will squash the image from the right side toward the left and from the bottom upwards.

* screensizeoffset_x = width
* screensizeoffset_y = height

`screensizeoffset_x 00`

`screensizeoffset_y 00`

# Example 

If your resolution is `640 480` and you put for example

`screensizeoffset_x 10`

`screensizeoffset_y -10`

`screenoffset_x -5`

`screenoffset_y 5`

You will get in the result:

This configuration is equivalent to the following configuration
in `batocera.conf`.

`es.customsargs=--screensize 650 470 --screenoffset -5 5`


The file `/userdata/system/es.arg.override` will be erased every time the CRT script
is executed. Backing up the file is recommended.

To persist the changes, execute `batocera-save-overlay`.