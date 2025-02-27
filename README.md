# DMX ArtNet record and run
 A way to record ArtNet data with Processing, and run a playback afterwards.

Our application have been using MadMapper to generate ArtNet DMX data for three different light installations. The installations needed to run for a longer period outside. Originally we used one MacMini with MadMapper to run the installations, but that just gives all kind of unneeded issues when tyying to setup a proper way of running the projects, and automating the open/close tine of the installations etc. Therfore we designed this software to be able to run the ArtNet data for each installation on a Raspberry Pi instead. Removing the need for MadMapper, and a regular computer.

## File structure
This repository consists of two Processing sketch folders. "record_artnet_dmx" and "run_artnet_dmx". These two applications need to be kept in the same overlying folder during the recording process, since they are referencing files inside each others subfolders.

## Record a DMX sequence
To record a DMX sequence via MadMapper using ArtNet you first need to setup MadMapper and the Processing software "record_artnet_dmx". Then you can just record the sequence you wish. 

Hint:<br>
A god way to setup madmapper to give a good playback result is to use the DMX record function in MadMapper. Amongst other features you can use this to record a sequence, edit the start and end position of the playback, and fade to/from black when starting/ending the sequence.

### Setting up MadMapper
Open MadMapper, and navigate to the DMX settings under preferences (MadMapper->Preferences->DMX). 
- Select ArtNet as a DMX output
- Enable the "Use unicast" setting.
- Select ethernet IP "127.0.0.1" as the "Interface" 
- Then use the (+) button to manually add each universe you will be sending data to. Each time edit the IP to "127.0.0.1" and the universe number to match your setup. 1-4 in my case.
See the image below for final setup for our application.

![DMX preferences](https://github.com/airlabitu/DMX-ArtNet-record-and-run/blob/main/settings/DMX%20preferences.png)

