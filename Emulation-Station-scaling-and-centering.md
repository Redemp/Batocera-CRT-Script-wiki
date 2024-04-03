Under Contruction

The script will create the file `es.arg.override` in the folder
`/userdata/system`

screensizeoffset_x 00

screensizeoffset_y 00

screenoffset_x 00

screenoffset_y 00

if your resolution is 640 480   and you put for example   screensizeoffset_x 10  screensizeoffset_y -10  screenoffset_x -5 screenoffset_y 5

you will get :

es.customsargs=--screensize 650 470 --screenoffset -5 5

so you can adjust your screen by using this file   es.arg.override (edited)

And each time your re-use the script.  the file `/userdata/system/es.arg.override` will be erased so make a backup.


You must put the offset not the resolution into /userdata/system/es.arg.override
