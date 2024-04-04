### How to add and test resolutions
  
  From terminal type
`switchres 320 240 60 -i switchres.ini -c`

It should output a single line similar to this: 

`Switchres: Modeline "320x240_60 15.660000KHz 60.000000Hz" 6.514560 320 333 364 416 240 242 245 261   -hsync -vsync`

Now we know that it works for you monitor profile. 

Now let's add it to `videomodes.conf`

Edit: `/userdata/system/videomodes.conf`

`320x240.60.00:320x240 60 Hz`

The first line `320x240.60.00` is what is read by switchres. 

The second line after `:` is what is displayed in video modes in Emulation Station. 

In this example it is `320x240 60 Hz`

You can name it to whatever you want but it is easier to name it to the resolution you added. 

That's it. Just save the file and the resolution is added. 