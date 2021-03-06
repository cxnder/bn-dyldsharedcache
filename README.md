# Dyld Shared Cache Parser
Author: **cynder (kat)**

_Dyld Shared Cache Support for BinaryNinja_

![BinaryNinja Screenshot](.github/sel.png?raw=true "Image Selection")

![BinaryNinja Screenshot](.github/sbui.png?raw=true "Disassembly View")

Without any of the fuss of requiring manually loading several unrelated images, or the awful off-image addresses, and with better output than IDA, Hopper, or any other disassembler on the market. 

## Installation + Usage

1. Open the plugin manager
2. Search for "Dyld" and install this plugin

### Usage:

1. Open Dyld Shared Cache file with BN
2. Select the Image you would like to disassemble
3. Congrats, you are now Reverse Engineering the Mach-O

## Description:

This project acts as an interface for two seperate projects; DyldExtractor, and ktool. Mainly DyldExtractor.

[DyldExtractor](https://github.com/arandomdev/DyldExtractor) is a project written primarily by 'arandomdev' designed for CLI standalone dyld_shared_cache extraction. It is *the* best tool for the job, and reverses the majority of "optimizations" that make DSC reverse engineering ugly and painful. Utilizing this plugin, Binja's processing should outperform IDAs, and wont require IDA's need for repeatedly right clicking and manually loading tons of modules.

This version of DyldExtractor has a lot of modifications (read: a lot of commented out lines) from the original designed to make it function better in the binja environment. 

[ktool](https://github.com/cxnder/ktool) is a multifaceted project I wrote for, primarily, MachO + ObjC Parsing.

It is mainly used for super basic parsing of the output, as we need to properly write the segments to the VM (and scrap all the dsc data that was originally in this file) so the Mach-O View knows how to parse it. 

## License

This plugin, along with ktool and dyldextractor are released under an [MIT license](./license). Both of these plugins are vendored within this project to make installation slightly simpler. 
