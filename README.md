# Pioneer DDJ-FLX4 Binding for VirtualDJ on Linux
This repository contains the required files to get a Pioneer DDJ-FLX4 working with VirtualDJ on Linux.

The files were recreated from scratch, as the built in device definition doesn't recognize the controller correctly due to Wine limitations and there doesn't seem to be a way to extract existing bindings from the program.
Wine seems to only support MIDI through ALSA, so any advanced audio routing one would expect from JACK or Pipewire is unavailable.

## Setup
The process to get up and running is rather straightforward:

1. Install VirtualDJ, preferrably in a separate wine prefix. We used the [Lutris install script](https://lutris.net/games/virtual-dj/) for the installs used to develop this mapping.
2. Open and close it once, so the relevant files and folders are generated.
3. Plug in your FLX4 and verify, the MIDI device is called `DDJ-FLX4 - DDJ-FLX4 MIDI 1`. If it's not, you'll have to modify the `drivername` property of the root element of FLX4.xml to match the name your ALSA reports.
4. Copy "FLX4.xml" into the folder located at `<WINE PREFIX ROOT>/drive_c/users/<YOUR USERNAME>/AppData/Local/VirtualDJ/Devices/`. This will allow VirtualDJ to recognize the FLX4 as a controller it knows and can map.
5. Copy "Pioneer DDJ-FLX4 - Custom Mapping.xml" into `<WINE PREFIX ROOT>/drive_c/users/<YOUR USERNAME>/AppData/Local/VirtualDJ/Mappers/`. This will give you basically the default behavior of FLX4 connected to VDJ on windows. Alternatively you can also create your own mapping.
6. Open VirtualDJ. If everything went as expected, you should see a new device popup for a "Pioneer DDJ-FLX4 Linux".

Happy mixing!