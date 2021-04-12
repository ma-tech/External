External Software
=================

This is a convinient packaging of software required to build and run some
of the Mouse Atlas software including: Woolz, the Woolz IIP server,
Woolz Qt based applications like WlzWarp and Woolz Motif iapplications like
MAPaint.
To build and install the software follow the instructions in the README files
along side the archive files in each of the directories. In many cases and
particularly on Linux systems these README files can be copied and then
edited and run as shell scripts to build and install the software.

The software libraries in the order that they should be built and installed
are:


|Software	|Required By	|Notes
|:--------------|:--------------|---------------------------------------------
|cJSON		|W		|
|Coin		|Q		|
|Jpeg		|IQWX		|The version here is known to work, system
|		|		|provided ones may work too.
|Tiff		|IQWX		|The version here is known to work, some older
|		|		|versions have been known to have problems
|		|		|with 16 bit image byte ordering, but system
|		|		|provided ones may work too.
|Log4Cpp	|I		|
|Fcgi           |I		|
|NIfTI		|IQWX		|
|PNG            |I		|
|QtColorPicker	|Q		|
|Regexp		|		|Possibly useful if building in a non POSIX
|		|		|environment (eg Windows).
|Xbae		|X		|The version here is known to work, system
|		|		|provided ones may work too.

Key to requirements:

+ W - (Woolz required for external file format support)
+ X - (HGU X11 Applications including MAPaint and MA3DView)
+ Q - (Woolz Qt Applications including WlzWarp and WlzViewer)
+ I - (Woolz IIP Server - WlzIIPSrv)
