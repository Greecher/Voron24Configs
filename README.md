# Greecher Voron 2.4R2 Setup, V2.5730 registered 7/23

This is the Klipper Config for my 300mm Voron 2.4. This is built out with everything I wanted to do, may add mods later, but as of now completely happy with it.

## About this repo

This is the real actual config that I run on my printer. This is the repository that is created from a push from my printer to share, but also backup in case of catastrophe.  For the use cases of this printer and mods deployed, maybe of use to someone else whom has those mods. ***Use at your own risk.***

## Goals for this printer
* A printer that would catch me up to date on what's new and available tech wise as of early to mid 2023, superceding my old and retired Hypercube Evolution, another self built printer that was wholly sourced by yours truly.
* A printer that gets used for printing functional parts. I commonly print in ASA now and still PLA when it doesn't matter as much.  I design most of what I consume, but occasionally will visit [Printables](https://www.printables.com), as well as share out my own designs there as well.
* Reliability, Repeatability, Usability & Print Quality - I don't necessarily care about absolute maximum print speed, but when I want a print, I want success.

## About the Printer's Hardware

This is a Voron 2.4R2 LDO kit built in early 2023.  Additionally I used [PIF](https://pif.voron.dev/) for my parts,as my previous printer died, and I was always limited in ABS/ASA material.  I cannot speak enough volumes about using the PIF program, as the comprehensiveness of understanding the parts you'll need, with your choice of mods & colors, to the beautiful quality of the prints made it a joy to build out this kit.

Here is a list of the final build & mods.

* Stealthburner with CW2 Toolhead - note the LDO kit comes with the latest pancake extruder motor as well as Bondtech gears.
* E3d Voron Revo - a slight variation of the revo with a Voron specific heat sink.
* Voron Tap - soon to be decommissioned in favor of Cartographer Survey Touch
* Nevermore chamber filter, also part of the stock LDO kit.  This works well on keeping my chamber temperatures constant and odor free, regulary at 60C after 20 minutes preheat for my ASA prints, and even 70C after 1 hour.
* [Nozzle Scrubber](https://www.teamfdm.com/files/file/188-decontaminator-purge-bucket/) was a drop dead simple install.  Note my X width as built is the natural 300, but my Y is 309.  Because of Stealthburner, had to do a final tweak of bed placement, but it works very well, and leaves me with a true 300x300 build area. 
* Octopus Pro mainboard.
* Updated to a Rasberry Pi 5 with SSD Hat to get away from issues with SSD failures and also performance, this replaced a OrangePi4 LTS (was available in Covid Pandemic times...).  Note the SSD hopefully is imune to having machine shut off without a proper shutdown (which you should always do anyways!).  Hardwired 5v/5A supply to mains for Pi, rest down there is stock other than a nicer touch screen I had available.  Note, had issues with FPS for crowsnest, so repurposed OrangePi to be just for camera.
* Crowsnest to a Logitech C920X webcam running off old OrangePi4 LTS.  This should help unload the pi as the webcam is high bandwidth, so maybe onboard ADXL will work properly now, maybe...
* A usb plugable adxl module driven by it's own raspberry pi pico, this is from [Nero's Youtube](https://www.youtube.com/watch?v=W_VHbT_tsZw&ab_channel=NERO3D).  Note, may try ADXL on Cartographer post install.
* A CanBus Toolhead board, the SB2209 from BigTreeTech.  This asside from allowing me to go full umbilical that drives the extruder, heater, fans and SB neopixels is a nice looking option that I find really reliable.  CanBus couldn't support the onboard ADXL chip, as it will be bandwidth limited, or is in my case, to only 60HZ, but everything else on the head (Extruder, Revo, Fans, Neopixels, Tap, w/ onboard temp sensor) has never failed me with the stock supply umbilical cable.
* Note the SB2240 was initially installed, but I had alot of issues with the board cutting out mid print.  This may have been a mfg issue, as they have now delisted the board altogether.  This may also have been a static charge issue, note there is maybe a reason to ground the motor to a gnd pin on SB2209 to alleviate issues (1/12/2025).
* Added 2 toolhead sensors, one below extruder teeth, one above.  This was at the same time I added the Filametrix toolhead filament cutter in prep for a TurtleBox AMS system.
* As said, am replacing Voron TAP with Cartographer probe, this may give back some lost y axis travel, which may suit the nozzle scrubber better.
* Installed [KAMP](https://github.com/kyleisah/Klipper-Adaptive-Meshing-Purging/blob/main/README.md) 7/9/2023, am using the following modules
*   Smart_Park (sets toolhead near print area for extruder heatup).
*   Line_Purge to add a line purge, again also near print area.
*   Adaptive_Meshing to do a much more tailored mesh to the actual print area
* Replaced stock wire nozzle scrubber with silicone brush (from Bambu A1), as old scrubber was kinda ineffective, and I needed to change for Cartographer probe anyways.  Made my own version of macro to do it.
* Changed over to OrcaSlicer as main gcode generator, and made updates to better suit.  Tuned up G32 to be a bit more efficient, ie only home x/y if not done already, don't rehome x/y, but only z post nozzle scrub.  This version ensures to make bed heat to final temp at the start, extruder to start @ 150C for TAP/Cartographer max temp, then do the calibrate, then properly set and ensure the extruder and bed temps before proceeding.

## Klipper Software Customization
* Sensorless X & Y homing, this [guide](https://docs.vorondesign.com/community/howto/clee/sensorless_xy_homing.html) made it a snap, and works excellently.
* Added in Cartographer software, and will soon add BoxTurtle AMS software also.

## Overall Experience
* The build was pretty flawless, as my bed has a very slight taco shape, but of only .14mm spread, more than acceptable.  Took the time to go through the tuning guides first, so I had no issues with getting printing well almost from the start.  This was in big part for 2 reasons, the LDO kit had everything needed, and the PIF parts had zero issues.
* The Discord server for VORON has sooo many helpful hints and people, use it whenever you get stuck!

