### How to add and test resolutions
  
Let's start with adding the resolution **384x224@60hz**

From terminal type

`switchres 384 224 60 -i switchres.ini -c`

It should output two lines similar to this: 

`Switchres: Calculating best video mode for 384x224@60.000000 orientation: normal`
`Switchres: Modeline "384x224_50 15.600000KHz 50.000000Hz" 7.378800 384 395 430 473 224 259 261 312   -hsync -vsync`

Now we know that it works for you monitor profile. 

Now let's add it to `videomodes.conf`

Edit: `/userdata/system/videomodes.conf`

`384x224.60.00:384x224 60 Hz`

The first line `384x224.60.00` is what is read by switchres. 

The second line after `:` is what is displayed in video modes in Emulation Station. 

In this example it is `384x224 60 Hz`

You can name it to whatever you want but it is easier to name it to the resolution you added. 

That's it. Just save the file and the resolution is added. 