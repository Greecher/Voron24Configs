# Greecher/Voron24Configs

This is the Klipper Config for my 300mm Voron 2.4. This is built out with everything I wanted to do, may add mods later, but as of now completely happy with it.

## About this repo

This is the real actual config that I run on my printer. This is the repository that is created from a push from my printer to share, but also backup in case of catastrophe.  For the use cases of this printer and mods deployed, maybe of use to someone else whom has those mods. ***Use at your own risk.***

## Goals for this printer
* A printer that would catch me up to date on what's available tech wise today (early 2023), superceding my old and retired Hypercube Evolution, another self built printer that was wholly sourced by yours truly.
* A printer that gets used for printing functional parts. I commonly print in ASA now and still PLA when it doesn't matter as much.  I design most of what I consume, but occasionally will visit [Printables](https://www.printables.com), as well as share out my own designs there as well.
* Reliability, Repeatability, Usability & Print Quality - I don't necessarily care about absolute maximum print speed, but when I want a print, I want success.

## About the Printer's Hardware

This is a Voron 2.4R2 LDO kit built in early 2023.  Additionally I used [PIF](https://pif.voron.dev/) for my parts,as my previous printer died, and I was always limited in ABS/ASA material.  I cannot speak enough volumes about using the PIF program, as the comprehensiveness of understanding the parts you'll need, with your choice of mods & colors, to the beautiful quality of the prints made it a joy to build out this kit.

Here is a list of the final build & mods.

* Stealthburner with CW2 Toolhead - note the LDO kit comes with the latest pancake extruder motor as well as Bondtech gears.
* E3d Voron Revo - a slight variation of the revo with a Voron specific heat sink.
* Voron Tap
* Nevermore chamber filter, also part of the stock LDO kit.  This works well on keeping my chamber temperatures constant and odor free, regulary at 60C after 20 minutes preheat for my ASA prints, and even 70C after 1 hour.
* [Nozzle Scrubber](https://www.teamfdm.com/files/file/188-decontaminator-purge-bucket/) was a drop dead simple install.  Note my X width as built is the natural 300, but my Y is 309.  Because of Stealthburner, had to do a final tweak of bed placement, but it works very well, and leaves me with a true 300x300 build area. 
* Octopus Pro mainboard.
* Minor under the hood items, as I went with a OrangePi4 LTS (easier and cheaper to aquire than the standard Raspy4 at this point in history), a variant with an EMMC drive to hopefully have a more secure feeling about not zapping my OS if printer gets turned off without a proper shutdown (which you should always do anyways!).  Also added a additional 5v buck converter to supply it, rest down there is stock other than a nicer touch screen I had available.
* Crowsnest to a Logitech C920X webcam.
* A usb plugable adxl module driven by it's own raspberry pi pico, this is from [Nero's Youtube](https://www.youtube.com/watch?v=W_VHbT_tsZw&ab_channel=NERO3D).
* A CanBus Toolhead board, the SB2240 from BigTreeTech.  This asside from allowing me to go full umbilical that drives the extruder, heater, fans and SB neopixels is a nice looking option that I find really reliable.  CanBus couldn't support the onboard ADXL chip, as it will be bandwidth limited, or is in my case, to only 60HZ, but everything else on the head (Extruder, Revo, Fans, Neopixels, Tap, w/ onboard temp sensor) has never failed me with the stock supply umbilical cable.
* Note the SB2240 uses the latest TMC2240 driver chip, and I am thankful that the Klipper team got this included in the current distro, only took like 6 weeks.
* Added in a filament sensor also, a self built one.

## Klipper Software Customization
* Sensorless X & Y homing, this [guide](https://docs.vorondesign.com/community/howto/clee/sensorless_xy_homing.html) made it a snap, and works excellently.

## Overall Experience
* The build was pretty flawless, as my bed has a very slight taco shape, but of only .14mm spread, more than acceptable.  Took the time to go through the tuning guides first, so I had no issues with getting printing well almost from the start.  This was in big part for 2 reasons, the LDO kit had everything needed, and the PIF parts had zero issues.
* The Discord server for VORON has sooo many helpful hints and people, use it whenever you get stuck!
* One minor, I blew a daughtercard on the SB2240 for the fans/leds when I misplugged it into toolhead board, but I had a spare when i finally debugged it, as it only affected the neopixels.

