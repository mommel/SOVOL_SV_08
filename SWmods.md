# What I modded and why

## Timelapse

As I found out, the Timelapse function was the cause that a longer print was failing after several hours, I added a macro:
```g-code
[gcode_macro TIMELAPSE_TAKE_FRAME]
gcode:
    M117 Actively skipping Timelapse
```
It does basically nothing beside notifying the user, that it skipped the Take Frame Process. 

----

## Disabled Obico

No need for me to have my printers controlled outside of my network.

----

## added Macros

I added some more macros for my needs.

__MANUAL_CLEAN__
 A macro that moves the head to the front in a useable height and heats the nozzle to 250. Than the printer informs (Text, Light and Sound) that it's ready for a manual clean. After 30 Seconds it continues with the normal NOZZLE_CLEAN macro.

 Why? Because the normal NOZZLE_CLEAN wasn't enough for my needs.
 
 __BETTER_LOAD_FILAMENT__
To prevent clogging or other issues when switching from a higher temp filament to a lower temp filament I trash some more filament.

----

## FLUIDD & Landing Page

I installed FLUIDD because I can and sometimes love to use Fluidd and other times mainsail.
This is not the first printer i use it that way, so i have an extra repo for this, that i can easily clone to the printers.
github.com/mommel/klipperlaunch
I configure mainsail in that case to the port 9888 and fluidd 9887 and let the html landing page be served to port 80, while the /api folder is rerouted to the mainsail api.