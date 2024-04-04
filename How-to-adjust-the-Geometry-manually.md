### How to adjust the Geometry manually 
 - Note: If you only use the CRT for Batocera i would advise you to adjust the horizontal position using the service menu first. 

From SSH type
`DISPLAY=:0 geometry 640 480 60`
or
`DISPLAY=:0 geometry 320 240 60`

Adjust the setting with a connected keyboard. 
Switch between different grids with the tab key on your keyboard.

When done press Enter and it will output something like this in the terminal
`Final geometry: 1.0:4:-2`
`Final crt_range: 15625.0-16200.0,49.5-65.0,1.665,4.693,8.326,0.159,0.191,1.020,0,0,192,288,448,576`

edit `switchres.ini `
In this example we have the monitor profile `arcade_15`

Change from` arcade_15` to `custom`
Default
`    monitor                   arcade_15`
After
`    monitor                   custom`

Same with the crt range
`    crt_range0                auto`
to
`    crt_range0                15625.0-16200.0,49.5-65.0,1.665,4.693,8.326,0.159,0.191,1.020,0,0,192,288,448,576`

Save the file and then make sure to save `switchres.ini` outside the userdata folder with
`batocera-save-overlay`

Then reboot
`reboot`

### Generate a new custom EDID file used for boot only for you custom monitor profile. (Optional)
**1)**
switchres 641 480 60 -f 641x480@60 -i switchres.ini -e
This will create a file named `custom.bin`

**2)**
SSH
`mount -o remount,rw /boot`

**3)**
Copy `custom.bin` to the folder
`/lib/firmware/edid/`
make sure it has the correct file permission (`0600`)
Mark file in WinScp and check file permission under Properties.
or do 
`chmod 600 /lib/firmware/edid/custom.bin`

**4)**
Open the `syslinux.cfg` file's in the following folders in Notepad++
`/boot/boot/`
`/boot/boot/syslinux/`
`/boot/EFI/`
`/boot/EFI/BOOT/`

You should now have 4 files open.

**5)**
Now find the line that says
`edid/arcade_15.bin`

Change it to

`edid/custom.bin`

**6)**
SSH
`batocera-save-overlay`
`reboot`