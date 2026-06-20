# Changelog

## [UNRELEASED]

### Added
 
 - something we added


### Changed

 - Updating the changelog to a modern markdown format with a roughly "keepachangelog" style. Hopefully I made good decisions about what changes I made and broke as few things as possible. Another alternative to the rest of the file is just wrapping it all in preformatting. -Jack/NuclearMonster

### Removed

 - something that was removed

### Fixed

 - something that was fixed

### 2008-04-04 Various contributors

* Solaris fixes
* Replace vsprintf function in bg\_lib.c with vsnprintf implementation started by Patrick Powell
* Compile bg\_\* files separately for each game module, as originally intended
* Write q3config\_server.cfg for the server, to avoid reseting client variables
after running a dedicated server
* Split image decoders into their own files
* OS X build updates for most compatibility
* Slackbuild
* Detect available resolutions and offer them in the in game menus
* A few botlib fixes
* Fix poppy captured audio when recording videos
* Extend console logging on crash errors
* Merge \*BSD platform definitions in q\_platform.h
* IRIX support
* Remove all the old bat/sh QVM building scripts
* Make master server used client configurable (cl\_master)
* Fix to QVM compilation on big endian architectures
* OpenBSD support
* Autocomplete key names
* Don't build client command completion on the dedicated server
* Don't apply colour escape chars on input fields
* Rewrite of the win32 dedicated console
* Improved Makefile startup time
* Build dedicated server binary on Windows
* Bump Q3\_VERSION to 1.35
* Replacement of platform specific backends with a generic SDL one
* Merge win\_net.c and unix\_net.c to net\_ip.c
* Demote input related console information to developer only so that it doesn't
spam the console every time input settings are changed
* PNG texture support
* Cleanup of tabulation in R\_LoadImage
* Fixes to console scrolling
* New x86\_64 vm that doesn't use gas
* Early out AABB collision optimisation
* Generate QVM dependicies in a better way
* Build process is quieter
* Replace horrendously long list of Makefile build rules with set of inference rules
* Allow CC to be overridden externally to the Makefile
* Move storage of console history from a cvar to a file in order to alleviate
security concerns
* Fix bug where transparent surfaces wouldn't draw over skyboxes
* Add input sanitising to various sound playing functions called from mods
* Explicitly set OpenAL distance attenuation model
* Increased the number of registers used for the opStack in the PPC vm from
12 to 16
* Fix endian issue in MDR loading
* Add cURL support for HTTP/FTP downloading
* Disable video command when not playing back a demo
* Print the SVN version string in Com\_Init()
* OpenAL device enumeration support
* Fix 100% CPU usage on idle dedicated servers
* Windows home directory support
* Improve correctness of AVI files created by video command
* Better SDL joystick support
* sv\_minRate
* \[cl|sv]\_packetdelay
* Various security fixes
* Fix JIT compiler code execution on NX-protected win32 OS
* Fix r\_overBrightBits variable getting ignored on Linux
* cl\_guid for semi-reliable server authentication
* Anisotropic texture filtering
* Video export doesn't crap out with sv\_pure 1 anymore
* Video export doesn't crap out when writing > 2Gb files anymore
* Fix to a bug where servers with long uptimes (\~27 days) would consume 100%
CPU if the running game did not set the nextmap cvar
* Some OSes no longer requires a vid\_restart when changing r\_fullscreen

### 2006-01-24 Various contributors

* Persistent console history
* Added code to sleep a bit when q3 has no focus and sleep a lot when it's
minimised (SDL only)
* Cull excess speaker entities when using OpenAL
* Fix the operation of the delete key in \*nix
* Only check the checksum on baseq3 pak0.pk3
* Overhaul of console autocompletion
* No longer does weird stuff like move the cursor inappropriately
* Autocomplete works with compound commands
* Special autocomplete on some commands e.g. \\map, \\demo
* Removed various hacks used to counter the original autocomplete code
* Fixed the ability to disable Ogg Vorbis
* s/i686/i586/ - see bug #2578
* Some sloppily coded mods call the Q3 sound API with NaNs -- sanitise this
* Removed advertising clause from BSD license as per mailing list discussion
* "make distclean" now does what you'd expect
* "make clean toolsclean" now does what "make distclean" did before
* GPL MD4 implementation

### 2006-01-16 Various contributors

* Move code/unix/Makefile to ./Makefile
* x86 OS X support
* "quake3" shell script as shipped with 1.32 (on linux) no longer needed
* Ogg codec support from Joerg Dietrich
* Fix to the gcc4/-O0 x86 JIT compiler bug
* Up the defaults for zone and hunk memory since some mods (UT) have large
memory requirements that will have increased versus 1.32b due to some of the
alignment fixes
* Dependency generation for the .asm files
* Remove FS\_SetRestrictions
* Add FS\_CheckPak0 for better error messages where dumb users are involved
* Added cl\_autoRecordDemo, which when enabled automatically records a new demo
on each map change
* Only display the g\_synchronousClients warning when it's appropriate
* Remove custom memcpy/memset code
* AVI video output
* Uses motion jpeg codec by default
* Use cl\_aviFrameRate to set a framerate
* \\video \[filename] to start capture
* \\stopvideo to stop capture
* Audio capture is a bit ropey
* General Makefile improvements
* Support for MinGW cross compilation
* NetBSD support from optical
* x86\_64 JIT bytecode compiler no longer disabled by default
* msvc project files updated and moved to win32/msvc
* Various alignment fixes
* Solaris (x86 and sparc) support from Vincent S. Cojot
* Fixed Altivec-based mesh rendering
* Ditch Mac OS 9 support
* Added a Makefile option USE\_LOCAL\_HEADERS which can be disabled to use system
headers if desired
* Detection of Altivec on Mac OS X
* SMP support with sdl\_glimp.c on Mac OS X.
* Add "very high quality" option (patch from Pascal de Bruijn)
* Support for RIFF files with zero length data chunks (yes they exist, and yes,
they're legal)
* Support for ccache. If you want it, add USE\_CCACHE=1 to Makefile.local
* Mac OS X now uses SDL backend, all Objective C removed
* Partial implementation of FS\_Seek for files in pk3s
* Implementation of r\_dlightBacks from Shane Isley
* OpenAL support, from BlackAura aka Stuart Dalton
* An abstract codec system, simplifying support for new formats
* Ignore in\_dgamouse setting if dga isn't available
* Removed hard coded mouse acceleration in \*nix input code
* Basically rewrote the lcc Makefile to be more sane
* Removed various bits of lcc that weren't built/needed
* General portability improvements
* Various variables added that aid packaging, from vapier
* Centralise architecture defines in q\_platform.h
* Replaced a bunch of inline and \_\_inline with ID\_INLINE
* Replaced a bunch of **i386** with id386
* General tidy up of asm preprocessor decisions
* Removed C\_ONLY from the dedicated server build
* Removed rule to build C++ (for splines) from the Makefile
* General decrufting
* Split USE\_SDL into USE\_SDL\_VIDEO and USE\_SDL\_AUDIO
* Various assorted bug fixes

### 2005-10-29 Various contributors

* nasm syntax asm ported to gas
* Disabled-by-default MD4 support
* cons build system removed
* Better FreeBSD support
* Makefile generates dependencies
* Some SDL sound tweaks
* qvm build tools and qvms are now built with the rest of the binaries
* q3asm-turbo from Phaethon
* Moved various displaced c and h files into more appropriate places
* A shitload (can I say shit?) of bug fixes -- see the svn log for details

### 2005-09-22 Tim Angus [tim@ngus.net](mailto:tim@ngus.net)

* MinGW port

### 2005-09-??

* SDL Stuff (icculus)
* x86\_64 (ludwig von angstenheimer)
* patches from a cast of thousands

# 2005-08-25 ioquake3 project started

# 2005-08-09 Quake 3 source code released!

### 2004-05-22 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* updated the xcode project from Apple's version
now with the latest vm\_ppc code

### 2004-05-21 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* fixed the Linux build to compile again on sid (glext.h and gcc3 warnings)
* 2 weeks ago, hacked up the source to compile on panther / xcode 1.1
several cleanups were needed, and VM support seems broke (hangs or crashes)
* got altivec optimisations from Apple (Kenneth Dyke)
merged back in
* looks like with the new code merge the VM support is back in and working

### 2003-09-15 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* import Q3 java master code, cleanups on monster

### 2003-08-31 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* loki\_setup hell
https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=626
http://zerowing.idsoftware.com/linux/q3a/index.html#glibc
text mode installer in loki\_setup image built on Mandrake 7.2 crashes on
some glibc 2.3 systems such as RH9 etc.  need to move to a different
version of the installer, and update old installers to keep them still
'installing' moving to build the setup binaries on Debian Woody systems
(glibc 2.2, text mode installer will no longer work on 2.1 systems) hacked
together a new setup, using setup tree from RTCW. would need a complete
revamp if a new full setup with new binaries is needed

### 2003-07-17 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* new cvsreport, testing per-module config

### 2003-01-19 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* building on both gcc 2.x and 3.x
added conf modules to check gcc version
ccache support

### 2003-01-13 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* tweaking around for gcc 3.x build
edit Conscript to change the compiler

### 2002-12-16 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* added pbEmit class to auth code, emit CD keys to local PB master

### 2002-11-14 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* up to latest makeself.sh

  * add both quake3.x86 and quake3-smp.x86 to setup
  * https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=573
console setup crash / glibc 2.3 (Debian Sid)
investigated, put together a workaround

### 2002-11-5 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* Linux building both smp and non-smp again. Will have to put both in setup
* added in\_subframe to toggle X subframe event handling
* reworked the timing code to be more reliable
* cleaned up dgamouse/in\_mouse code, removed unnecessary dgamouse var
* made the mouse grabbing an in\_nograb cvar, no longer a compile time option
in\_nograb 1 force in\_dgamouse 0 and r\_fullscreen 0 (any of those two will b0rk)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=565
mouse issues on Suze 8.1 - related to subframe event timing
added code chunk to detect broken X timing and disable subframe
* tweaked the subframe/X bug workaround to be less paranoid

### 2002-10-28 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* no longer blocking demo recording if g\_synchronous clients != 0
only sending out a warning (everyone does g\_sync 1 ; record ; g\_sync 0)

### 2002-10-21 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* building final mod sdk setups (added lcc bins, added link to q3asm-turbo in readme)

### 2002-10-8 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* quickfix cl\_maxpackets > 125 brings back to 100

## 1.32 release ---

### 2002-10-7 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* made the 'demo' command case-insensitive on extension match (it was confused by demo FOUR.DM\_68)
* mouse wheel scrolling with in\_mouse 1 + window mode was not working, fixed (DI didn't catch)
* removing on-the-fly pk3 build from Linux setup, using the finalized ones now
added 'pk3' option to cons for toggle of pk3 building

### 2002-10-5 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* updated win32 mod sdk (in win32/mod-sdk-setup)
added q3asm and lcc source
updated the .bat to build VMs

### 2002-10-3 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* linux mod sdk, wrote the bulk of the scripts

### 2002-9-30 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* ATVI Quake 3 1.32 Patch #9
rolling back to the way it was before, leaving 1v1 force vote exploit, the fix was worse than the bug
from comment on bug #9 in tracker:

&#x09;actually the fix is worse than the original bug

&#x20;    after the fix, voting when you are alone on the server was no longer working
it was kinda intended in the fix, that you would have to be at least two to pass a vote .. but
it is an oversight.

&#x20;    calling a vote in a 1v1 game against a bot fails immediately
     (calling a vote in any situation where there's only 1 live player fails)

     Say a server's running some lame custom map that you have but a friend doesn't. You can't go
     on the server and change it to the map you want to play, so he ends up having to auto-dl it at
     8K a second just so you can switch from it.

     This particular 2 clients, vote / quit exploit would involve too many changes to fix properly.
     I am reverting back to the old version, and leaving as WNF 










### 2002-9-29 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=50
added Wheel support to the DirectInput code IN\_DIMouse (in\_mouse 1)
tweaked the Wheel mouse reading for in\_mouse -1 (old win32 input code)
handle correctly when zDelta is > 120
provide an in\_logitechbug cvar to handle buggy Logitech MouseWare driver sending wheel events twice

### 2002-9-26 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* ATVI Quake 3 1.32 Patch #38
adding trap\_SetPbClStatus, reliably checks for PB presence before enabling PB in UI

### 2002-9-25 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=551
SVF\_CLIENTMASK, fixed a typo
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=555
pushed cl\_maxpackets upper limit to 125 (from 100) per CPMA Arqon's request

### 2002-9-24 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* ATVI Quake 3 1.32 Patch #33
PB reporting sv\_paused cvar hacked, fixed SV\_CheckPaused to use a Cvar\_Set
* ATVI Quake 3 1.32 Patch #24
added \[skipnotify] from RTCW, use to display in the console only, but not on client screen
(also fixes pb\_msgprefix and pb\_sv\_msgprefix)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=553
using correct error message if listen server starting as cl\_punkbuster 0 sv\_punkbuster 1
* ATVI Quake 3 1.32 Patch #35
text auto wrap in UI code was eating the last word if it was wrapping
fixed in Q3 and TA UI (this bug could have affected the server print message also)
* some updates to the win32 cons post-build process

### 2002-9-21 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* adding bspc cons build script

### 2002-9-19 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=552
disconnect reason is transmitted in the disconnect command and processed into com\_errorMessage
(similar to RTCW behaviour)
added UI for com\_errorMessage cvar in baseq3/, if client is kicked/dropped/disconnected for whatever reason
(this is already functional in TA)
* ATVI Quake 3 1.32 Patch #9
failing vote if there's only one voting client (fixes exploit on 2-player server where one player votes then disconnects, forcing vote to pass)
* ATVI Quake 3 1.32 Patch #5
removed the userInfoChanged message (was a debugging leftover)
* ATVI Quake 3 1.32 Patch #18
rcon was not properly fixed yet, this only showed up for PB commands
changed the rcon parsing again to be more reliable

### 2002-9-18 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=549
the demo command has a list of compatible protocols, it will loop through 66 67 68
you can do '/demo four' and it will try four.dm\_66 four.dm\_67 four.dm\_68
or you can explicitely give a '/demo demoname.dm\_??'
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=551
added SVF\_CLIENTMASK (0x00000002), works only with \<= 32 players
set bitmask of players to which send entity

### 2002-9-17 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=550
rcon bug fix
* some scons updates for win32 (post build)
* 1.32rc2

### 2002-9-06 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* updated completely the setup system:
fixed cons stuff to build setup with cons -- release setup
working from new setup codebase with some custom patches:
https://bugzilla.icculus.org/show\_bug.cgi?id=52
https://bugzilla.icculus.org/show\_bug.cgi?id=53
checked that BSD support was still in (brandelfing and symlinks) .. will have to get tester feedback
bumped version to 1.32rc1
TODO: update the windows .VCT (standalone setup and auto-update)

### 2002-9-04 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=543
backport from RTCW 1.4 code
rcon commands where sent after being tokenized and rebuilt
that was breaking any quoting, for instance 'rcon g\_motd "hooka pooka"'
added Cmd\_Cmd() to retrieve the un-tokenized command and transmit as is on both ends
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=542
b0rked text wrapping in connect screen
was a missing sizeScale in q3\_ui/, and a bad param in ui/
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=540
backport fix to pk3 reordering, happens when clearing the references, bad order from connection may break stuff
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=527
TA ui/, quickfix to netSource (mod stuff, doesn't affect TA)
* cleaned up broken old DO\_WIN32 stuff in cons scripts
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=526
typo in models2.shader
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=443
Linux client: sub-frame timing of key/mouse events
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=453
added mousewheel support: wheel to scroll, ctrl+wheel to scroll faster, shift+wheel to scroll history
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=545
bumped server count to 4096
* keep around: **asm** **volatile** ("int $0x03");
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=516
moved screenshots to backend with a new RC\_SCREENSHOT render command
fixes the r\_smp 1 garbled screenshots

### 2002-8-29 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=539
new VM code from Raven's Sof2
* cons / qvmtools build system fixes
* had to get a new qe3.ico again (resource compiler error)
http://vasin.hypermart.net/eei.htm
* updated, basic testing on win32, merging back in trunk
* merged bug-539 branch back into trunk, officialize the new VM code

### 2002-8-26 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=472
linux client: handle ctrl+space situations (could leave space locked on + space not working with ctrl on)
* update the build system, build q3lcc and q3asm etc. on demand
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=62
fixed invisible players/entities

### 2002-8-23 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=536
fixing donedl being ignored after autodl if map\_restart'ed (propagate from RTCW)
ignoring multiple map\_restart (propagated from RTCW)
* reworked the server 'client text ignored' message to only trigger	when there's actually a message that doesn't get to the game VM

### 2002-8-18 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=528
ydnar: reorg bits in the drawsurf sort index, push MAX\_SHADERS to 2^12
* commented out some debug stuff in java auth server
* added FAQ item with Linux \& BSD patch to handle broadcast on multiple interfaces

### 2002-8-15 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=534
fixing rcon being broken on NT/XP with > 23 days uptime (or so)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=525
changed the rcon buffer size to avoid overflows and dropping part of the message

### 2002-8-14 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* hacked in some experimental win32 stuff to the cons files
(win32 recognition and pk3 installs .. very very experimental but I needed it for win32 dev)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=521
ui/ and q3\_ui/ : added text auto wrapping in the connection screen drawing (server message)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=531
removed the MPlayer stuff from the server browsers
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=505
enabled back the ignore if protocol is != (fixes Wolf servers showing in browser)

### 2002-8-10 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=500
propagated IP banning fix from RTCW

### 2002-8-08 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* propagate additional sv\_lanForceRate fix from RTCW

### 2002-8-07 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* added trap\_FS\_Seek

### 2002-8-05 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=50
fixed the DI mouse init procedure

### 2002-8-05 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* removed sv\_allowanonymous, was dummy and polluting the serverinfo
(sv\_allowanonymous was designed to flag wether server was public or not, but that's replaced by g\_needpass)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=514
sv\_strictAuth (default 1): server variable to control wether strict CDKEY auth should be performed
this is required if you want reliable cl\_guid on the server
extended the getIpAuthorize (server->auth message) syntax
sending the fs\_game at all times (default 'baseq3'), dummy sv\_allowAnonymous 0, strict auth flag
NOTE: 1.31 server on baseq3 sends a getIpAuthorize packet like:
processing packet: getIpAuthorize -1230824753 217.128.77.195  0
the auth server will mistakenly read fs\_game as '0'
* TAGGED the master / auth source as pre-1\_32
will need to go back to this to comment out all my debugging crap

### 2002-8-04 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* cleaned master server stuff, client was prompting master.quake3arena.com,
server was sending heartbeats to master3.idsoftware.com
both point to 192.246.40.56, unified to master.quake3arena.com
the MPlayer master, master.quake3world.com doesn't exist anymore, switched it to master.quake3arena.com

### 2002-8-02 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* added auth server source, reorganized
* auth server name / master key optionally set on command line for master and auth servers
* auth and master config in build system
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=524
changed default GL driver from libGL.so to libGL.so.1
see LSB 1.2 spec: http://www.linuxbase.org/spec/refspecs/LSB\_1.2.0/gLSB/libgl.html
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=480
applying the 'no cp command' experimental fix for beta phase
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=462
backported from RTCW, fix to packet fragmenting emission
FIXME: there is some verbose code that we have to take out in the final version (grep for #462)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=475
backported from RTCW, don't get dropped if the server changes map while connecting (ignore outdated cp)
* PROTOCOL BUMPED TO 68

### 2002-8-01 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* Linux: dedicated build was not setting up signal handler like the full client does
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=522
SplashDamage bugfix, now clearing client gentity before GAME\_INIT call (instead of after)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=498
fixed NET\_AdrToString to print the port as unsigned int (for ports > 1^^15, was showing negative)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=501
maintain IP in userinfo sent to game
* checking in master server source

### 2002-7-31 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=513
https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=506
porting fix from RTCW codebase. client re-orders its pk3s to scan in the same order than the server
this eliminates several 'Invalid .PK3 file referenced' situations (caused by client not referencing the same thing as server)
* fixed border remnants in ta ui
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=517
ERR\_DROP if PB client off / server on conflict when starting local server
* quickfix to q3 ui / punkbuster detect in server browser
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=458
code fix, no more taunt spam
* cons install of PB .so files
* correct MOD\_KAMIKAZE and MOD\_JUICED in TA games.log

### 2002-7-29 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* q3 ui: completed confirmation prompts and messages (added UI\_ConfirmMenu\_Style \& UI\_Message)
* ta ui: backported 'conditionalopen' from RTCW (conditionalopen \<cvar\> \<menu1\> \<menu2\>)
* ta ui: confirmation prompt for punkbuster enable/disable etc.
* added the win32 DLLs to pb/win32/

### 2002-7-28 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* ta ui: sv\_punkbuster in StartServer menu
* ta ui: added cl\_punkbuster in server browser
* view filters are in a modal dialog
* new files: filter.menu menus.txt (pak3.pk3 updated)
* fix broken link in Linux FAQ

### 2002-7-27 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* ta ui: PB display in the browser, in its additional tab, with sorting

### 2002-7-26 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* PB UI: for baseq3/ AND missionpack/
q3\_ui: Punkbuster: Enable/Disable in server broswer (cl\_punkbuster)
q3\_ui: PB logo, PB Yes/No in browser (TODO: validate this to be working)
q3\_ui: added sv\_punkbuster toggle in start server menu
* automated building of the new PK3s, unix/Conscript-pk3

### 2002-7-25 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* added PB build scripts on Linux, fixed the Linux build

### 2002-7-12 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=511
fixing re.SetColor crash for widescreen displays (q3dm11)
was calling to the renderer while not registered

### 2002-6-19 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* r\_roundImagesDown 0 + map q3dm16 -> tr\_image.c ResampleTexture crash
buffer overflow because of resample to 2048x..
xian\_q3dm12\_leftwall4fin.jpg 1152x384
bumped one buffer byte p1\[1024] -> byte p1\[2048], added a safe check

### 2002-6-14 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=493
propagate a renderer fix from RTCW. fixes a one-frame visual glitch when mod code
registers a shader after drawsurfaces are generated but before the frame is rendered

### 2002-6-12 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* added cons and pcons to unix/, updated the build script

### 2002-5-24 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
towards a new Q3 release?
some bug fixes require protocol change, or mod code/mod interface change to be fixed properly
this is a biz decision, dunno yet if we are going to want a new protocol (probably not)
-> have to create a branch for the 1.31b, i.e. backwards compatible with 1.31 'Stable-1\_31'
and put the 1.32 specific / protocol changes on trunk
no telling what will go in SOS in the end .. probably 1.32

### 2002-5-5 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=491
adding a sv\_lanForceRate (defaults to 1) to turn on/off server forcing rate of LAN clients
(only affects LAN dedicated clients - dedicated 1, default behaviour forces LAN clients to 99999 rate)

  * https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=470
fixing potential overflows with cl\_cdkey (propagated from RTCW)
  * cons-based build system (imported from Wolf, was partly written for mod tools release already)
building with SMP on by default
  * better #ifdef SMP handling ('disabled at compile time' message)
  * https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=494  
Q\_vsnprintf for vsprintf calls in the core
not putting this in game code as we'd need a vsnprintf implementation in bg\_lib.c

### 2002-4-5 Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=462
taking out the fix which was found broken and incomplete

### 2002-8-4  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* adding NO\_MOUSEGRAB define (select in the Makefile)

### 2002-2-4  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* applying Gareth's SMP patch
* count number of CPUs (Sys\_ProcessorCount in unix\_shared.c), default r\_smp appropriately
* bumping version to 1.32
* if XInitThreads fails, set r\_smp to zero

### 2002-28-2  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=462
send potential remaining fragmented packets before sending a gamestate

### 2002-26-2  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=455
removed old libMesaVoodooGL.so loading code
Voodoo cards should use XF4/DRI, that load code was outdated and confusing people with broken OpenGL

### 2002-16-1  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=441
adding brandelf calls to the setup building process so that our binaries run on BSD

### 2002-1-1  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* updated FAQ with BSD info (bug #441)
* FAQ update on CLIENT\_UNKNOWN\_TO\_AUTH
* FAQ update for proper strace usage

### 2001-12-12  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* Q3 1.31 point release
updating build\_setup.sh to new pk3 files
(baseq3/pak7.pk3 missionpack/pak2.pk3)
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=395
adding quake3.xpm icon, and modified the setup accordingly to put symlinks
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=390
ignoring SIGTTIN SIGTTOU

### 2001-06-12  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=402
bug with full scene

### 2001-04-12  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=398
cg\_bobup cheat protect
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=399
fixed Setup > System > Driver info crash
* checked in code/spank.sh script, perform checksuming

### 2001-18-09  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=371
propagating sound code fixes from Wolf to Q3

2001-11-08  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* setup script was still broken, damn shell expansion
the exit code for Q3 was always zero instead of $?
propagating the fix to Wolf

### 2001-11-04  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=382
modified challenge code for motd to be truly random

### 2001-10-31  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
Moved updated q3asm and lcc source at the toplevel, MissionPack/q3asm
and MissionPack/lcc

### 2001-10-29  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=381
build system is now functional

### 2001-10-21  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* updated Sys\_LoadDll code on linux to search in the following order:
#1 current directory
#2 fs\_homepath
#3 fs\_basepath
this was needed to make mod development easier

### 2001-10-09  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=51
the code to buffer the redirection was in there but disabled? (Com\_Printf)
enabled it back
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=52
connection issues / userinfo
client side fix, instead of sending 'connect \<userinfo\>' packet
we now send 'connect "\<userinfo\>"'

### 2001-10-08  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=371
added a PROT\_READ to the mmap call
this was needed to go around a bug in glibc i586 i686, memset doing read access
since the audio\_fd is opened O\_RDWD this is harmless to Q3

### 2001-10-07  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* updating from SOS
S\_WriteLinearBlastStereo16 C/asm is back in snd\_mix.c (Graeme)
r\_showtris r\_shownormal cheat protections
* Sys\_LoadDll changes:
removing -debug search when loading native dlls
changing the fatal aborts when not finding native from release only to debug only (was a misfeature)
used to search in cd\_path which is bogus, now searching in pwd if basepath fails
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=275
fixed r\_fullbright not being cheat protected / was a CVAR\_LATCHED|CVAR\_CHEAT issue

### 2001-09-06  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* updated from SOS, some changes to qcommon/unzip.c (statics)

### 2001-08-27  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=3
Added some code in CL\_InitDownloads to use FS\_ComparePaks and print out information about server-referenced paks that are missing on the client. It is a first step, allows to get precise information about what can cause a connection to fail (typically when the user is sent back to the main screen).

### 2001-08-22  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=86
fixed sound bug (with Graeme hints)

### 2001-08-20  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* made sure Sys\_Printf doesn't get into an endless loop if logfile is on
fixed qconsole.log issues, +set logfile 1 +set fs\_debug 1 was crashing (any OS)
fixed logfile 1 / ttycon 1 issue, didn't exit properly (same endless looping)
also fixes an issue reported by q3f team
* changed rcon commands from Com\_DPrintf to Com\_Printf so that they show up in the console
(with IP information)

### 2001-08-19  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* fixed https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=91
(autodownload toggle in q3 ui)
* fixed https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=76
g\_password issue
* fixed https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=93
cheat protecting r\_lodCurveError
* wontfix https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=92

### 2001-08-18  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* more fixes to the 7-button mouse code (linux only)
* updated faq about gamma slider
* added "servers don't show up in ingame browser" to faq
* added Alt+Enter toggle for fullscreen/windowed (linux)

### 2001-08-16  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
reconfiguring CVS repository to give access to Gareth

* testin gareth's access

### 2001-08-03  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=85
fixes in the setup code for older bash versions

### 2001-08-02  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* commented out assembly implementation of S\_WriteLinearBlastStereo16, using modified C implementation from Zaphod
need to check performance: https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=88
* finished const declarations in CG\_Trace calls, was needed in pmove\_t declaration and some other functions
cgame/cg\_local.h : CG\_trace trap\_CM\_BoxTrace
game/bg\_public.h : using const in pmove\_t trace functions prototypes
(fixes gcc warnings: assignment from incompatible pointer type)

### 2001-07-26  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=78
mapped K\_MOUSE4 K\_MOUSE5

### 2001-07-23  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=5
more fixes, handling meta characters and various kinds of backspace

### 2001-07-22  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=5
after testing feedback, fixed more stuff:
better backspace, works with putty and potentially more terminals
* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=51
band aid fix to rcon status, incresed MAX\_PUSHED\_EVENTS from 256 to 1024
(adds 28kb of mem requirements)

### 2001-07-21  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=2
using XF86 Gamma extension to set the gamma in game from the menus
(previous behaviour was to set /r\_gamma and restart, renderer relying on s\_gammatable)
restoring initial gamma on GLimp\_ShutDown

### 2001-07-19  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=5
first usable version of dedicated console
added history and completion functionality
ready for some testing
still some TODOs and FIXMEs:
keep the currently edited line when going back from history exploration
edit the current line with cursor, insert mode etc.

### 2001-07-18  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* starting TAB completion and history for the dedicated server (tty console)
removed Sys\_ConsoleOutput (unused)
removing bogus nostdout variable
cleanup of a big chunk of code that Bernd commented out and scheduled for deletion
moved completion code from client/cl\_keys.c stuff into qcommon/common.c, Field\_CompleteCommand(field\_t\*)

### 2001-07-13  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* fixed https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=8
screenshots overwrites
* fixed https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=31
DOUBLE SIGNAL FAULT

### 2001-07-11  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* fix for french keybards / console toggle / bound to XK\_twosuperior

### 2001-07-10  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=19
cleanup of the keyboard code, adding com\_developer message in case XLookupString would fail

### 2001-07-10  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=33
using our custom handlers for X errors, should make things more robust
(X docs say some X errors are not fatal, but the default X handler exits the app anyway)

### 2001-07-08  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=19
keyboard state issues, fixed the sticking with ctrl key (thks relnev)

### 2001-07-07  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* closing https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=13
the fixes to bug #9 solved this one too
\* checking in to SOS

### 2001-07-05  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* work on https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=9
filesystem code changes:
updated the documentation in files.c to the current system
added correct fs\_homepath fs\_basepath fs\_cdpath scanning to FS\_SV\_FOpenFileRead
(fixes description.txt not found, and probably a few other linux issues)

### 2001-06-29  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* fixed setup issues (graphical/console)
https://zerowing.idsoftware.com/bugzilla/show\_bug.cgi?id=6

### 2001-06-26  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* bug tracker is online at https://zerowing.idsoftware.com/bugzilla
authentication, use login: bugs password: b00gies
for now, using it as the linux bug tracker, possible use for more OSes and programs if anyone is interested.
\* tweaked the graphical setup to send to bugs@idsoftware.com on errors instead of support@lokigames.com

### 2001-06-19  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* fixed generated launch script /usr/local/bin/quake3, exit $\* should be exit

### 2001-06-18  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* rebuilt 1.29f setups, released as 1.29f-beta1 'Q3 1.29f linux-i386 Jun 19 2001'

### 2001-06-10  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* rebuilt against PR source, packaged 1.29b setups

### 2001-05-25  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* graphical setup, based on Loki's setup tool (GPL)

### 2001-05-22  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* changed fs\_basepath to fs\_homepath, according to Graeme's changes (probably missed this change?)
this fixes the q3key prompting at each game startup

### 2001-05-20  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* rebuilding 1.28b, various fixes on linux build:

* SetProgramPath was renamed to Sys\_SetDefaultCDPath in unix\_shared.c
updated unix\_main.c accordingly
* some prototypes in qgl.h are guarded by #ifndef GL\_VERSION\_1\_2 (ARB extensions)
those prototypes are needed by linux\_glimp for importing functions and casting, added a #ifdef **linux**
(not a clean solution)
* game/q\_shared.h
little endian / big endian functions have been added
gcc generates warnings about functions being unused .. inlined them
* cgame/cg\_marks.c
// TTimo
// gcc warning: might be used uninitialized
float sInc = 0.0;
float s = 0.0;

### 2001-05-15  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)
\* fixes to linux Makefile for bspc 2.1h
\* various updates to 1.28b on linux

### 2001-05-09  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

\* R. Duffy reverted game/bg\_pmove.c PM\_CheckDuck, was a merging screup on my side
\* updated setup to 1.27z, removed the .so from the setup distribution (they were in 1.27g because of issues)
FIXME: gotta get pk3's first



### 2001-05-04  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

\* fixes to gcc, building RC for 1.27s



### 2001-05-01  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

\* added qcommon/huffman.c to the Makefile
\* gcc -Wall:
commenting out
CL\_Netchan\_Encode CL\_Netchan\_Decode (cl\_net\_chan.c)
Netchan\_ScramblePacket Netchan\_UnScramblePacket (net\_chan.c)
SV\_Netchan\_Encode SV\_Netchan\_Decode (sv\_net\_chan.c)



### 2001-04-26  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

\* fixed dedicated server crash when entering the VM\_COMPILED qagame on a mod (some statics lacked initialization)



### 2001-04-25  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

\* added $(Q3POBJ) to clean target (cleanup of platform-dependent objects)
\* more make clean improvements



### 2001-04-23  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

\* cleanup the mod selection code, remove duplicates
\* some issues with release builds, my main development box doesn't build stable binaries with release settings
removing -fomit-frame-pointer seems to fix (there's probably a performance hit)
see OMIT-FRAME-POINTER.txt



### 2001-04-13  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

\* checked in a first set of merged files



### 2001-04-06  Timothee Besset [ttimo@idsoftware.com](mailto:ttimo@idsoftware.com)

\* merged back the core linux parts to make 1.27g linux build from the Source Safe tree again



### 2001-02-27  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* CVS: tag with changes as of today
cvs tag id1-27j-loki01027

\\\* code/qcommon/msg.c: numFields loop (SOS).
\\\* code/qcommon/files.c: ue Q\\\_stricmp (SOS uses stricmp, was strcmp).
\\\* code/game/q\\\_shared.h (Q3\\\_VERSION): 1.27j. Also
MAX\\\_STRING\\\_TOKENS upped from 256 to 1024 (SOS).

\\\\\\\* code/server/sv\\\\\\\_snapshot.c (SV\\\\\\\_AddEntitiesVisibleFromPoint): see below.
	\\\\\\\* code/game/g\\\\\\\_public.h (SVF\\\\\\\_NOTSINGLECLIENT): added (SOS).

	\\\\\\\* code/server/sv\\\\\\\_ccmds.c: see below.
	\\\\\\\* code/game/g\\\\\\\_main.c: g\\\\\\\_gametype cvar now userinfo (SOS).

	\\\\\\\* code/game/g\\\\\\\_active.c (SendPendingPredictableEvents): new (SOS).
	\\\\\\\* code/game/bg\\\\\\\_misc.c: new SOS (sos010227)

	\\\\\\\* SOS: new update sos010227.
	









### 2001-02-22  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* CVS: now in sync with last SOS and cleanup up
cvs tag id1-27i-loki01022

\\\* code/ui/ui\\\_shared.c: below.
\\\* code/ui/ui\\\_main.c: leftover code!
\\\* code/server/sv\\\_world.c: below.
\\\* code/server/sv\\\_snapshot.c: below.
\\\* code/server/sv\\\_init.c: below.
\\\* code/server/sv\\\_game.c: below.
\\\* code/server/sv\\\_client.c: below.
\\\* code/server/sv\\\_ccmds.c: below.
\\\* code/server/sv\\\_bot.c: below.
\\\* code/server/server.h: below.
\\\* code/renderer/tr\\\_surface.c: below.
\\\* code/renderer/tr\\\_shader.c: changed assert to early return.
\\\* code/renderer/tr\\\_shade\\\_calc.c: below.
\\\* code/renderer/tr\\\_shade.c: below.
\\\* code/renderer/tr\\\_scene.c: below.
\\\* code/renderer/tr\\\_mesh.c: below.
\\\* code/renderer/tr\\\_local.h: below.
\\\* code/qcommon/vm\\\_x86.c: cleanup.
\\\* code/qcommon/vm.c: below.
\\\* code/qcommon/unzip.c: below.
\\\* code/qcommon/qcommon.h: below.
\\\* code/qcommon/files.c: below.
\\\* code/qcommon/cvar.c: cleanup.





### 2001-02-21  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/qcommon/common.c: cleanup.
\* code/qcommon/cm\_trace.c: cleanup.
\* code/qcommon/cm\_patch.c: cleanup.
\* code/qcommon/cm\_public.h: cleanup.
\* code/game/q\_shared.h: cleanup.
\* code/game/q\_shared.c: cleanup.
\* code/game/q\_math.c: cleanup.
\* code/game/g\_syscalls.asm: changed (once more) floor,ceil etc.
\* code/game/g\_spawn.c: cleanup.
\* code/game/g\_session.c: cleanup.
\* code/game/g\_cmds.c: cleanup.
\* code/game/g\_client.c: cleanup.
\* code/game/g\_arenas.c: cleanup.
\* code/game/bg\_slidemove.c: cleanup.
\* code/game/bg\_pmove.c (PM\_CheckDuck): old call to trace?
\* code/game/bg\_misc.c: cleanup.
\* code/game/be\_aas.h: dead code.
\* code/game/ai\_dmq3.c: cleanup. One clear/copy switched?
\* code/game/ai\_dmnet.c: more //\*/. Why oh why not DEBUG....

\\\* code/client/snd\\\_mix.c: below.
\\\* code/client/snd\\\_dma.c: below.
\\\* code/client/keys.h: cleanup.
TODO: #error in q3\\\_ui/keycodes.h ?

\\\\\\\* code/client/client.h: cleanup.
	\\\\\\\* code/client/cl\\\\\\\_main.c: misplaced bracket. Cleanup.
	\\\\\\\* code/client/cl\\\\\\\_keys.c: below.
	\\\\\\\* code/client/cl\\\\\\\_cin.c: below.
	\\\\\\\* code/client/cl\\\\\\\_cgame.c: cleanup.
	TODO: define assert for Win32 or guard my assertions.

	\\\\\\\* code/cgame/cg\\\\\\\_syscalls.c: below.
	\\\\\\\* code/cgame/cg\\\\\\\_servercmds.c: below.
	\\\\\\\* code/cgame/cg\\\\\\\_players.c: cleanup.

	\\\\\\\* code/cgame/cg\\\\\\\_newdraw.c: remember to diff against cg\\\\\\\_newDraw.c
	in SOS (mixed case).
	TODO: get id to use cg\\\\\\\_newdraw.c, and to remove cg\\\\\\\_newDraw.c/cpp.

	\\\\\\\* code/cgame/cg\\\\\\\_main.c: below.
	\\\\\\\* code/cgame/cg\\\\\\\_local.h: below.
	\\\\\\\* code/cgame/cg\\\\\\\_event.c: below.
	\\\\\\\* code/cgame/cg\\\\\\\_drawtools.c: below.
	\\\\\\\* code/cgame/cg\\\\\\\_draw.c: cleanup.
	\\\\\\\* code/cgame/cg\\\\\\\_consolecmds.c: dead code.
	\\\\\\\* code/bspc/qbsp.h: below.
	\\\\\\\* code/bspc/l\\\\\\\_poly.c: below. 
	\\\\\\\* code/bspc/l\\\\\\\_math.c: cleanup.
	\\\\\\\* code/bspc/bspc.c: cleanup.
	\\\\\\\* code/bspc/be\\\\\\\_aas\\\\\\\_bspc.c: cleanup. 
	\\\\\\\* code/bspc/aas\\\\\\\_map.c: kept comments - merge loss at their end?
	\\\\\\\* code/bspc/aas\\\\\\\_file.c: cleanup. 

	\\\\\\\* code/botlib/be\\\\\\\_interface.c: this file is plain impossible. There
	are layers of code made dead with /\\\\\\\* \\\\\\\*/ and the resurrected by
	//\\\\\\\* or // /\\\\\\\* or variations of this. I reverted to exact mirror
	image of SOS to be sure - short of removing it's too easy to mistake 
	live code for dead one.
	Later: have to change 5 occurrences to avoid gcc complaints about
	nested comment tokens.
	TODO: somebody please get rid of the cruft in here.

	\\\\\\\* code/botlib/be\\\\\\\_ai\\\\\\\_move.c: redundant typedef.
	\\\\\\\* code/botlib/be\\\\\\\_ai\\\\\\\_chat.c: assertions on signed string index.
	Note: this is not in my ChangeLog - ouch.
	TODO: use  gcc -fsigned-char on all platsforms to enforce Win32
	TODO  behavior (PPC has a default unsigned char, Intel has not).
	\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_sample.c (AAS\\\\\\\_TraceClientBBox): one code block
	was placed in different location, and one FPE hack not used. I would
	expect that divide by zero will still occur here.

	\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_reach.c: below. 
	\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_cluster.c: cleanup. 
	\\\\\\\* CVS: the last tag (below) marks the version with a lot of history
	and additional comments. I am now bringing the codebase in sync with
	SOS as of yesterday, cleaning out comments, dead code and other
	differences to minimize a diff - in a valiant if futile attempt to
	roll back changes into the id codebase.
	Note: I ignore the $SOS$ - these are unfortunate but will change
	in the same awkward way at their end.
	Note: I stick to #if 0 instead of C comments around dead code id
	kept (nested comments issue). The commentary is changed to sosYYMMDD
	and includes the token DEAD.










### 2001-02-20  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* CVS: update, then tag current version as
cvs tag id1-27i-loki010219

\\\* SOS: patched up to sos010219.

\\\\\\\* code/qcommon/cm\\\\\\\_trace.c (CM\\\\\\\_Trace): fabs on sphere offsets (SOS).
	\\\\\\\* code/game/bg\\\\\\\_slidemove.c (PM\\\\\\\_StepSlideMove): stepSize vs. STEPSIZE (SOS).
	\\\\\\\* code/game/bg\\\\\\\_pmove.c (PM\\\\\\\_CheckDuck): fix in stand up check (SOS).
	\\\\\\\* code/bspc/bspc.c (main): -capsule (SOS).
	\\\\\\\* code/bspc/qbsp.h: below (SOS).
	\\\\\\\* code/bspc/be\\\\\\\_aas\\\\\\\_bspc.c (capsule\\\\\\\_collision): added (SOS).
	\\\\\\\* code/bspc/aas\\\\\\\_map.c (CapsuleOriginDistanceFromPlane): added and used (SOS).
	\\\\\\\* code/bspc/aas\\\\\\\_file.c (AAS\\\\\\\_WriteAASFile): removed diagnostics recently
	added. No matter how long you wait, they'll always get you ;-).
	\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_cluster.c: enabled LogWrites, different flood (SOS).

	\\\\\\\* SOS: patching up to snapshot sos010219. 
	Note: For brevity, I use as marker sosYYMMDD now instead of bkYYMMDD, to 
	distinguish from changes not in SOS.

	\\\\\\\*  CVS: tagged current version before patching up with SOS.
         cvs tag id1-27i-loki010216-bsd










### 2001-02-16  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/server/sv\_init.c: DLL\_ONLY sets sv\_pure to 0 and ROM.
TODO: determine good sv\_pure policy for DLL-only servers.

\\\* code/renderer/tr\\\_shade\\\_calc.c: my\\\_ftol implementation (BSD).

\\\\\\\* code/unix/Makefile: FreeBSD sections.
	TODO: include target-specific Make-freebsd etc.,
	include a Make-local not in CVS for build preferences,
	and generally clean up this mess.
	\\\\\\\* code/unix/unix\\\\\\\_glw.h: guard #error
	\\\\\\\* code/unix/linux\\\\\\\_snd.c: soundcard.h location (BSD).
	\\\\\\\* code/unix/linux\\\\\\\_glimp.c: guard system headers.
	Later: added Joystick stubs.
	Note: linux\\\\\\\_ etc. prefixes start to loose meaning as we
	re-use most of this on UNIXes anyway. I didn't use Raf's
	freebsd\\\\\\\_joystick.c but instead put generic stubs here.
	TODO: introduce generic -DNO\\\\\\\_JOYSTICK flag.
	\\\\\\\* code/renderer/tr\\\\\\\_local.h: my\\\\\\\_ftol guard.
	\\\\\\\* code/renderer/qgl.h: FreeBSD guards.
	\\\\\\\* code/qcommon/vm\\\\\\\_x86.c: sys/types include on FreeBSD.
	\\\\\\\* code/qcommon/md4.c: Win32 pragma guard.
	\\\\\\\* code/qcommon/common.c: Com\\\\\\\_Memcpy/Memset external.
	\\\\\\\* code/game/q\\\\\\\_shared.h: added FreeBSD defines. 
	\\\\\\\* code/game/q\\\\\\\_math.c (BoxOnPlaneSide): FreeBSD conditional.
	TODO: check whether we have/need the assembly version anyway.
	\\\\\\\* code/client/snd\\\\\\\_mix.c: use C fallback on FreeBSD.
	Note: all of the above changes from the original port by Rafael Barrero.

	\\\\\\\* CVS: tagged current version before merging FreeBSD related changes.
         cvs tag id1-27i-loki010215-ppc










### 2001-02-15  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/unix/Makefile: BSD related changes.
\* code/cgame/cg\_draw.c: hacked phone jack rendering check for Debug.
TODO: finish Debug, fix CG\_DrawDisconnect !!!

\\\* code/unix/vm\\\_x86.c: error on compile attempts. Fight redundancy!
\\\* code/qcommon/vm\\\_x86.c (VM\\\_CallCompiled): dummy for linkage on PPC.
Note: DLL\\\_ONLY is the global Makefile option for DLL-only builts.
Currently only executed on Linux.
\\\* code/unix/unix\\\_main.c: \\\*ppc postfix for DLLs. Ignored the changes
to redundant code (have to remove the unused Un/LoadDll/API calls).
\\\* code/server/sv\\\_game.c (VMA): changed macro (see below). PPC.
\\\* code/qcommon/vm.c (VM\\\_DllSyscall): see lengthy commentary by Ryan.
The existing VM code makes certain assumptions about the layout of
varargs on the stack, which fall apart with call conventions that
don't even put all parameters on the stack (gcc on PPC, register-rich).
Using a dedicated memory area as our own stack. This should actually
be the default behavior.
Later: make vm\\\_\\\* cvars INIT/ROM for DLL\\\_ONLY target.

\\\\\\\* code/qcommon/common.c: PPC change (from Ryan Gordon).










### 2001-02-07  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/unix/unix\_main.c: disabled FPE for debug for the time
being (that is, until I can figure out
Program received signal SIGFPE, Arithmetic exception.
RB\_BeginSurface (shader=0x449572e0, fogNum=0) at ..//renderer/tr\_shade.c:307
307 tess.shaderTime = backEnd.refdef.floatTime - tess.shader->timeOffset;
without any NaN's involved.
TODO: unmask other FPE's selectively (see Mike's Tribes2, no getenv though).



### 2001-02-06  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* SOS: up to date with todays snapshot.
Note: got the date wrong, comment used was bk010205. Duh.

\\\* code/server/sv\\\_snapshot.c (SV\\\_UpdateServerCommandsToClient): below.
\\\* code/server/sv\\\_main.c (SV\\\_ReplacePendingServerCommands): new (SOS).
\\\* code/server/server.h: reliableSent (SOS).

\\\\\\\* code/renderer/tr\\\\\\\_shade.c (ProjectDlightTexture): see below.
	\\\\\\\* code/renderer/tr\\\\\\\_scene.c: see below.
	\\\\\\\* code/renderer/tr\\\\\\\_public.h: see below (SOS).
	\\\\\\\* code/renderer/tr\\\\\\\_local.h: additive light support (SOS).

	\\\\\\\* code/qcommon/cm\\\\\\\_trace.c (CM\\\\\\\_Trace): new tw.sphere.use branch (SOS).

	\\\\\\\* code/game/g\\\\\\\_spawn.c: notta, notq3a entities (SOS).
	\\\\\\\* code/game/ai\\\\\\\_dmq3.c: MAX\\\\\\\_ACTIVATEAREAS search (SOS).
	
	\\\\\\\* code/client/cl\\\\\\\_cgame.c: see below.
	\\\\\\\* code/cgame/cg\\\\\\\_syscalls.c (trap\\\\\\\_R\\\\\\\_AddAdditiveLightToScene): below.
	\\\\\\\* code/cgame/cg\\\\\\\_syscalls.asm: see below (trap\\\\\\\_R\\\\\\\_AddAdditiveLightToScene).
	\\\\\\\* code/cgame/cg\\\\\\\_public.h: CG\\\\\\\_R\\\\\\\_ADDADDITIVELIGHTTOSCENE (SOS).
	
	\\\\\\\* code/bspc/l\\\\\\\_math.c: new VectorLengthSquared, removed rotate/matrix (SOS).
	\\\\\\\* code/bspc/bspc.c (BSPC\\\\\\\_VERSION): was 2.1e, now?
	\\\\\\\* code/bspc/be\\\\\\\_aas\\\\\\\_bspc.c (BotImport\\\\\\\_Trace): CM\\\\\\\_BoxTrace sig. (SOS).
	\\\\\\\* code/bspc/aas\\\\\\\_file.c (AAS\\\\\\\_WriteAASFile): SOS.
	\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_sample.c (AAS\\\\\\\_DeAllocAASLink): SOS.

	\\\\\\\* code/unix/unix\\\\\\\_main.c (Sys\\\\\\\_LoadDll): do not load from installdir
	in NDEBUG (confusing relic from old Makefile). Postfix -debug.so
	for debug binaries to let both builds coexist.

	\\\\\\\* code/unix/Makefile: updated install targets and VERSION.

	\\\\\\\* Win32: build from SOS snapshot.
	Note: Unix CR/LF in \\\\\\\*.dsw/\\\\\\\*.dsp fucks up MSVC++.










### 2001-02-02  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* SOS: all changes up to today.

\\\* code/server/sv\\\_init.c (SV\\\_TouchCGame): added. Also memset
on reallocated client data (SOS).
\\\* code/qcommon/qcommon.h: see below.
\\\* code/qcommon/cvar.c (Cvar\\\_SetLatched): new (SOS).
\\\* code/qcommon/cm\\\_trace.c: more sphere test fixes (SOS).
Note: SOS encryption key expired and updated by MrElusive.

\\\\\\\* code/qcommon/cm\\\\\\\_patch.c (CM\\\\\\\_TraceThroughPatchCollide): 
	fix from MrElusive, fall through curved corner floors (q3dm17).
	Later: also in SOS (so is shadow FPE fix).

	\\\\\\\* Win32: can't get an unadulterated SOS snapshot to build.
	First, fix CR/LF back again (Linux client converts all).
	 find . -name '\\\\\\\*.ds\\\\\\\*' -print
	 alias dos2unix='recode ibmpc..lat1' 
	 alias unix2dos='recode lat1..ibmpc'
        Next, find a \\\\\\\*.dws that works? Nope, no cigar.
	









### 2001-02-01  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* Win32: have to update dsp/dsw/etc. files in CVS, too.

\\\* CVS: tag previous version before update
cvs tag id1-27h-loki010131-beta3

\\\\\\\* code/game/q\\\\\\\_math.c (Q\\\\\\\_rsqrt): guard, #ifndef \\\\\\\_\\\\\\\_linux\\\\\\\_\\\\\\\_ 
	for assert (for Win32 build).
	TODO: assert replacement for Win32?
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_qmenu.c: see below.
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_players.c: see below.
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_controls2.c: float const with f postfix
	Note: Win32 C4305 warning. Somebody at id has been doing
	a lot of these recently as well...

	\\\\\\\* code/cgame/cg\\\\\\\_players.c (CG\\\\\\\_PlayerShadow): applied fix by 
	MrElusive, removed FPE hack (player shadows on zero mormals).
	Prolly in this evenings' CVS.

	\\\\\\\* code/server/sv\\\\\\\_game.c: new signatures (capsule again).
	\\\\\\\* code/server/server.h: new signatures (SV\\\\\\\_Trace,ClipToEntity).
	\\\\\\\* code/server/sv\\\\\\\_bot.c: new signatures (above).
	\\\\\\\* code/qcommon/cm\\\\\\\_trace.c: a truckload of changes. Math
	code added before moved upwards. Capsule traces added all
	over the place, old box traces moved in conditional
	branches, functions renamed and wrapped. Eliminated some
	of the previous' versions deadcode to keep diffs smaller.
	TODO: once a point release is out and reasonably bug
	TODO  free, remove // bkYYMMDD annotations where SOS related.

	\\\\\\\* code/qcommon/cm\\\\\\\_public.h: new signatures in prototypes.
	\\\\\\\* code/qcommon/cm\\\\\\\_patch.c: dead code re-enabled, new
	sections (conditional branches for spheres) added to 
	several trace functions.
	\\\\\\\* code/qcommon/cm\\\\\\\_local.h (CAPSULE\\\\\\\_MODEL\\\\\\\_HANDLE): added.
	\\\\\\\* code/qcommon/cm\\\\\\\_load.c (CM\\\\\\\_TempBoxModel): capsules.

	\\\\\\\* code/game/q\\\\\\\_shared.h (Q3\\\\\\\_VERSION): 1.27i now (new QVM traps).

	\\\\\\\* code/game/g\\\\\\\_syscalls.asm: see below.
	\\\\\\\* code/game/g\\\\\\\_public.h (SVF\\\\\\\_CAPSULE): added (SOS). Also
	G\\\\\\\_ entry poiints for capsule traces.

	\\\\\\\* code/client/cl\\\\\\\_cgame.c: see below.
	\\\\\\\* code/cgame/cg\\\\\\\_syscalls.c: see below.
	\\\\\\\* code/cgame/cg\\\\\\\_syscalls.asm: see below.
	\\\\\\\* code/cgame/cg\\\\\\\_public.h: new capsule trace code (SOS).










### 2001-01-31  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* Win32: test compile (WinCVS, MSVC++). Have to guard isnan.
Note: too much shit going on....



### 2001-01-30  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* CVS: update for patching up (pre-1.27i).

\\\* SOS: new changes (new collision detection primitives).
Now Version 1.27i.
TODO: start testing using DLL's (QVM code is out of sync).





### 2001-01-25  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* SOS: caught up till today (below).
\* code/qcommon/cm\_trace.c: new functions added: RotatePoint,
TransposeMatrix, CreateRotationMatrix (SOS).
(CM\_TransformedBoxTrace): new rotation code used here.

\\\* code/q3\\\_ui/ui\\\_demo2.c: sizeof(extension). SOS.
\\\* code/game/g\\\_cmds.c (G\\\_SayTo): CON\\\_CONNECTED.
\\\* code/game/ai\\\_main.c: HOOK added (SOS).
\\\* code/botlib/be\\\_aas\\\_move.c (AAS\\\_HorizontalVelocityForJump):
correct fix for FPE occurring (SOS).
\\\* code/game/ai\\\_dmq3.c: initmove.viewoffset (SOS).

\\\\\\\* code/game/q\\\\\\\_math.c: guard asser/isnan with Q3\\\\\\\_VM (q3asm).
	TODO: define Com\\\\\\\_Error based assert macro? NDEBUG?










### 2001-01-24  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/server/sv\_ccmds.c (SV\_MapRestart\_f): some debug.
TODO: map\_restart 0 disconnects external client in 1.27h?

\\\* code/renderer/tr\\\_image.c (LoadTGA): added some commentary
and dead code based on fixes from GtkRadiant (Leonardo found
flipped TGA's).





### 2001-01-23  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* BETA3: finished testing, ready to upload to id FTP.
Later: neither the FreeBSD beta not the Linux Beta3
uloaded. Beta2 not yet released, and clients get
disconnected with Beta2 and Beta3 on SV\_MapRestart\_f.



### 2001-01-22  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/client/cl\_main.c (CL\_InitDownloads): undid yesterday (SOS).
\* code/botlib/be\_aas\_sample.c (AAS\_DeAllocAASLink): guard print (SOS).
\* code/server/sv\_client.c (SV\_DirectConnect): VM\_Call disconnect (SOS).
\* code/qcommon/files.c (FS\_ListFilteredFiles): trailing slashes (SOS).
\* code/game/g\_cmds.c (SetTeam): print change (SOS).
Note: the above plus VectorClear(v1) (below) are todays SOS changes.

\\\* code/cgame/cg\\\_players.c (CG\\\_PlayerShadow): ignore bogus
(all zero) planes. This caused FPE in ProjectPointOnPlane.
TODO: why does trace return zero normal planes?
Note: gdb seems totally at loss with vec3\\\_t arrays....

\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_sample.c (AAS\\\\\\\_TraceAreas): FPE.
	NaN in uninitialized v1 that wasn't supposed to be referred 
	to in this branch. 

	\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_move.c (AAS\\\\\\\_HorizontalVelocityForJump): 
	FPE divide by zero (zero zvel, zero t) for jump estimates.

	\\\\\\\* code/client/cl\\\\\\\_main.c (CL\\\\\\\_Frame):1856. uivm==NULL on
	client after server crashed.
	TODO: check that uivm always non-NULL for client.
	TODO: do setenv(FX\\\\\\\_NO\\\\\\\_SIGNALS) to avoid exit errors...

	\\\\\\\* code/unix/linux\\\\\\\_glimp.c (GLW\\\\\\\_SetMode): added "Indirect"
	Mesa token to software rendering detection. Reworded error
	output and added drivername.
	TODO: measure framerate instead?










### 2001-01-21  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* SOS: caught up with changes up until today.

\\\* code/server/sv\\\_init.c (SV\\\_SetConfigstring): gentity != NULL

\\\\\\\* code/server/sv\\\\\\\_client.c: connect to "{all bots" server.
	\\\\\\\* code/renderer/tr\\\\\\\_init.c: JPEG extension on  screenshots
	\\\\\\\* code/qcommon/files.c: modes based on mods, fs\\\\\\\_basegame

	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_demo2.c: dm3 extension (demo names, protocol).

	\\\\\\\* code/game/g\\\\\\\_client.c: savedEvents\\\\\\\[] removed.
	\\\\\\\* code/game/bg\\\\\\\_misc.c: event sequence fixes.
	\\\\\\\* code/client/snd\\\\\\\_dma.c (S\\\\\\\_StopBackgroundTrack): different use.	
	\\\\\\\* code/client/cl\\\\\\\_main.c: demo file handling changed (names).
	Also CL\\\\\\\_InitDownloads: always next download.

	\\\\\\\* code/cgame/cg\\\\\\\_servercmds.c: cg\\\\\\\_thirdPerson.
	\\\\\\\* code/cgame/cg\\\\\\\_weapons.c: see below.
	Also CG\\\\\\\_ShotgunPattern: different call (seed parameter).

	\\\\\\\* code/cgame/cg\\\\\\\_main.c: see below.
	\\\\\\\* code/cgame/cg\\\\\\\_local.h: new cg\\\\\\\_noProjectileTrail Cvar.
	\\\\\\\* code/cgame/cg\\\\\\\_effects.c (CG\\\\\\\_BubbleTrail): early out (above).

	\\\\\\\* code/bspc/l\\\\\\\_poly.c (BOGUS\\\\\\\_RANGE): increased.
	\\\\\\\* code/bspc/bspc.c: applied patch up to "2.1e"










### 2001-01-18  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/ui/ui\_main.c: below.
\* code/q3\_ui/ui\_main.c: UI\_HASUNIQUECDKEY comment.
Note: mods have to return qfalse. See Bug #2890 in Fenris.



### 2001-01-17  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* BETA2: finished testing, uploaded to id's FTP for release.



### 2001-01-16  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* CVS: checking in preparation for Beta2.
cvs tag id1-27h-loki010116-beta2

\\\* SOS: new bspc "2.1e". No change on 1.27h.

\\\\\\\* TEST: patch-up seems to work fine. No new files have been added
	to the linkage (i.e. the ft2/ files now added), so we might not be
	feature complete.

	\\\\\\\* code/game/g\\\\\\\_active.c (ClientThink\\\\\\\_real): id MISSIONPACK
	conditional in addition to the ones I added earlier.
	\\\\\\\* code/qcommon/files.c: REJECT. Linux hack for userdir threw it off.
	\\\\\\\* code/qcommon/unzip.c: REJECT. CRC-32 section removed.
	Later: unused tempB

	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_syscalls.asm: REJECT. Start/StopBackgroundTrack.
	\\\\\\\* code/ui/ui\\\\\\\_syscalls.asm: REJECT. syscalls ids from 1.27h 
	as of SOS (floor/ceil - will this ever get straightened out)
	\\\\\\\* code/win32/win\\\\\\\_input.c: REJECT. g\\\\\\\_pMouse edit.
	\\\\\\\* ui/menus.txt: REJECT. Replaced with 1.27h version.
        Note: some more due to $SOS$.
	
	\\\\\\\* ui/: new scripts.
	cinematicmenu.menu, demo\\\\\\\_quit.menu, ingame.txt, serverinfo\\\\\\\_old.menu
        vid\\\\\\\_restart.menu

	\\\\\\\* code/ft2/ttconfig.h: below.
	\\\\\\\* code/ft2/sfconfig.h: below.
	\\\\\\\* code/ft2/pstables.h: below.
	\\\\\\\* code/ft2/psnames.c: below.
	\\\\\\\* code/ft2/psdriver.h/c: below. 
	\\\\\\\* code/ft2/keys.h: below. 
	\\\\\\\* code/ft2/ftbbox.c: new in 1.27h
	
	\\\\\\\* code/cgame/cg\\\\\\\_newdraw.c: beware: cg\\\\\\\_newDraw.c gets lost in diff easily.

	\\\\\\\* code/cgame/cg\\\\\\\_rankings.c: file removed from SOS.
	









### 2001-01-15  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* Patch-up: patching up from RC4 to 1.27h current.
No changes since 010112 snapshot.
ln -s sos010112/ work
diff -urbB sos001204-rc4/ work > work.diff
ln -s cvs-1.27g/ work
patch -p0 \< work.diff  > work.patch
find cvs1.27g/ -name '\*.rej' -print

\\\* SOS: adding the remaining SOS snapshots to CVS.
cvs import Quake3\\\_sos sos001211 pr1-27g-win32-001211
Note: at this point id warned about repository corruption.
Watch out for the syscall stuff in particular.
cvs import Quake3\\\_sos sos010104 pr1-27g-win32-010104
cvs import Quake3\\\_sos sos010108 pr1-27h-win32-010108
cvs import Quake3\\\_sos sos010110 pr1-27h-win32-010110
cvs import Quake3\\\_sos sos010112 pr1-27h-win32-010112
Note: the first 1.27h might be the public (server only)
beta released, the second one was post release. Beware
of source files added and removed (botlib headers, FT2).
Note: why so late? Don't ask...





### 2001-01-08  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* SOS: id's working up to 1.27h (server side fix for
Guard exploit seems to force earlier release). Updating
CVS (most of the changes are debug code put in and
then disabled, plus some fixes as below). Next patching
up to current SOS.



### 2001-01-07  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* Makefile: need to rework this for multiple platforms.
We also need null/null\_vm.c for platforms where we don't
have JIT (assembly emit).



### 2001-01-04  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/q3\_ui/ui\_connect.c (UI\_DisplayDownloadInfo): time
information for current (vs. start of download) is wrong,
thus negative 1 "estimated time", as well as transfer
rate just negative downloadSize. Not fixed.

\\\* code/unix/unix\\\_main.c (Sys\\\_ParseArgs): added.
Note: for support/us, to identify builts. This is only
a skeleton right now - if I ever feel the need to support
more than "-v" and "--version" I'll have to flesh this out.

\\\\\\\* code/unix/linux\\\\\\\_glimp.c (signal\\\\\\\_handler): see below.
	\\\\\\\* code/unix/unix\\\\\\\_main.c (Sys\\\\\\\_Exit): added an abstraction
	layer for exit/\\\\\\\_exit/assert/raise issues.
	Note: need both a better debug/backtrace handling, and
	have to find a way to determine why/where the alleged
	startup/exit errors happen...










### 2001-01-03  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/game/g\_mem.c (G\_Alloc): ERR\_DROP initiated by
addbot commands for large sv\_maxclients, allegedly
caused segfaults in 1.17. Not reproducible.
TODO: recover more gracefully from failure to add bot?

\\\* code/renderer/tr\\\_light.c (R\\\_LightForPoint): Tim Angus
reports a crashbug with nolight maps. Also assertion in
R\\\_SetupEntityLightingGrid, might want conditional there.
DONE: fixed crash on LightForPoint for nolight maps.

\\\\\\\* code/qcommon/qcommon.h: NUM\\\\\\\_SERVER\\\\\\\_PORTS. A feature 
	request to increase this, or make it more flexible
	otherwise (Fenris).
	TODO: id decision on more flexible NUM\\\\\\\_SERVER\\\\\\\_PORTS.










### 2001-01-02  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/unix/snapvector.nasm: fixed FPU bit (the current
one had reserved bits off, behavior should not change).
\* code/qcommon/vm\_x86.c: fixed symbols (below).
\* code/unix/ftol.nasm: FPU bits weren't correct (duh).
DONE: shoot-though floor (q3dm5)
DONE: cursor-in-rect off  (TA/Player model selection)
Note: in gdb, "disassemble \<funcname>" is your friend.

\\\* code/cgame/cg\\\_public.h:  CG\\\_MEMSET is set to 100. In
cg\\\_syscalls.asm it's 101. If I change it I get Bad trap 100
from the cgame VM code, so the 1.27g "official" VM code
uses it.

\\\\\\\* code/unix/linux\\\\\\\_common.c: have to fall back to C, the
	current assembly is buggy...
	\\\\\\\* code/unix/Makefile (linux\\\\\\\_common.o): added.
	Later: also for dedicated. Less portable this way.
	TODO: C\\\\\\\_ONLY for dedicated on non-i386 only?

	\\\\\\\* code/qcommon/common.c: do not use memcpy/memset under Linux.
	\\\\\\\* code/unix/linux\\\\\\\_common.c: added Andrew's assembly port.
	TODO: C\\\\\\\_ONLY for Com\\\\\\\_Memset/Memcpy? Conditionals are fubared.

	\\\\\\\* code/qcommon/vm.c (VM\\\\\\\_Init): use Win32 defaults (do not
	use DLL's by default). This exposes DLL rounding errors
	(damage through floors), and we don't want DLL's used by
	default anyway.
	TODO: why vm\\\\\\\_ui default of 1?

	\\\\\\\* code/botlib/l\\\\\\\_precomp.c (SourceWarning): removed assert.

	\\\\\\\* code/game/bg\\\\\\\_lib.c (acos): defined, but we don't actually
	use it except where the cg\\\\\\\_syscalls.asm trap is used.

	\\\\\\\* code/game/g\\\\\\\_public.h: missing lots of trap tokens.
	\\\\\\\* code/game/g\\\\\\\_syscalls.c: missing lots of traps.
	\\\\\\\* code/game/g\\\\\\\_syscalls.asm: more inconsistent hooks, were:
	 equ floor					-111
         equ ceil					-112
	 equ testPrintInt			        -113
         equ testPrintFloat			        -114
	now changed to match cg\\\\\\\_syscalls.
	Note: fixed this in UI earlier, how did this slip through 
	the diffs against SOS?
	
	\\\\\\\* code/game/g\\\\\\\_syscalls.c: no acos hook.
	\\\\\\\* code/cgame/cg\\\\\\\_syscalls.c: no acos hook.
	\\\\\\\* code/cgame/cg\\\\\\\_syscalls.asm: has acos hook as -112
	Note: report from Tim Angus. The acos function is in bg\\\\\\\_lib.c
	which is linked only into ui (not q3\\\\\\\_ui). That means we are
	using libc acos right now?
	Note: QVM traps are negative?

	\\\\\\\* BSD/Irix: tagged current CVS (not all of the below) as
	 cvs tag id1-27g-loki010102-bsd1
	for BSD work (Rafael Barrero). Also be used for Irix update.










### 2001-01-01  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* SOS: adding the remaining SOS snapshots to CVS.
cvs import Quake3\_sos sos001201-rc3 pr1-27f-win32-001201-rc3
cvs import Quake3\_sos sos001202 pr1-27f-win32-001202
cvs import Quake3\_sos sos001204 pr1-27g-win32-001204-rc4
This is the codebase to which the Linux branch has been patched
up. I can't verify whether this is identical to the RC4 codebase
as the tag doesn't work (but can check against the ZIP file..)
cvs import Quake3\_sos sos001211 pr1-27g-win32-001211
The above snapshot contains a (post-release?) fix to ui\_syscalls
in ui/ and q3\_ui/. This change has been used in Linux (Beta1 and
above). At this point, id discouraged further use of SOS due to
repository corruption on their end. No further snapshots were
taken since.

\\\* Fenris: since the release of the Beta1 bugs have been
maintained at http://fenris.lokigames.com/. I am going to
list issues here as they get fixed.





### 2000-12-21  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/renderer/tr\_font.c: graceful silence with old mods?
\* code/botlib/l\_precomp.c (SourceWarning): graceful exit if old mod?



### 2000-12-20  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/server/sv\_ccmds.c (SV\_MapRestart\_f): see below.
\* code/qcommon/vm.c: currentVM is 0x0 in VM\_ArgPtr.
In VM\_Call, oldVM was NULL - made conditional the
reset of currentVM to oldVM.



### 2000-12-18  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* BETA1: closed Linux beta release. Stripped debug
and release binaries, DLL's, and pak4.pk3. CVS checkin,
will be tagged as
cvs tag id1-27g-loki001218-beta1
Later: id added a pak5.pk3 to the Win32 point release,
added this to the BETA1 best.

\\\* code/qcommon/vm\\\_x86.c: C37F.
\\\* code/unix/snapvector.nasm: C37F.
Note: short of any real evidence, I gamble and use max.
precision (as well as default Linux precision, but NOT
Win32 precision). It seems that precision change is not
really an issue (despite Graeme's claim that the cursor
in the menu was/is off). I also pick the roundiung behavior
that is seemingly used by ANSI and gcc (but possibly not
Win32 \\\_ftol depending on build).





### 2000-12-15  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/unix/Makefile: added snapvector.o
\* code/unix/unix\_shared.c: #if 0'ed the old snapvector code.
\* code/unix/snapvector.nasm (Sys\_SnapVectorCW): two new
assembly functions from AndrewH that explicitely set the
FPU control word to convert vec3\_t, to ensure cross-platform
behavior for both DLL and QVM.

\\\* code/unix/ftol.nasm (Q\\\_ftolC37F): for globals.

\\\\\\\* code/unix/unix\\\\\\\_main.c: took out global FPU manipulation.
	For clarity this should be VM only.
	\\\\\\\* code/qcommon/vm\\\\\\\_x86.c: added prototypes for the ftol
	library. To select a specific behavior for the entire VM,
	set ftolPtr accordingly.
	Later: the GCC ftol function of course affect the stack
	(there is no "declspec naked"). The problem seems to be 
	that the VM never handles the stack in a way compatible 
	to regular gcc C functions. For some odd reason \\\\\\\_ftol seems 
	to do the right thing under Win32. All 4 control words 
	implemented at the moment work just fine with the menus.

	\\\\\\\* code/unix/ftol.nasm: added a small library of "safe" qftol
	variations that explicitely set the control word to the
	relevant (4) possibilities.










### 2000-12-13  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/qcommon/vm\_x86.c: an entire day spent trying to nail
the ftol issues. It breaks down like this: id used to use
an unsafe (no setting FPU control word) fistp. That seemingly
caused subtle physics bugs which nobody cared about in 1.17.
They then changed the UI code, and ran into the UI bugs:
menu entries shifted to the right, fonts vanishing. Then
they switched to using \_ftol. Then they had to reproduce
the old behavior for the physics code due to public outrage.
My original port used a simple (long)float cast, which gcc
seemingly compiles to code that does OR 0C00 on whatever
current control word (precision unchanged). This breaks the
menus. If I use the unprotected fistp instead, which should
(Linux 037F default) use "nearest/even", then my menus are
correct. That would mean Win32 \_ftol in id's compile does
the same, only that would require /qifist or some equivalent
compile flag, which I can't find. Two disassemblies of \_ftol
I got from others showed OR 0C00 as part of the default (ANSI)
behavior.



### 2000-12-13  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/game/bg\_pmove.c (PmoveSingle): trap\_SnapVector.
The one true and single call to snap velocity.
Note: bspc/map.c:void SnapVector(vec3\_t normal)
qcommon/cm\_patch.c:void CM\_SnapVector(vec3\_t normal)
game/q\_shared.h: #define SnapVector(v) {v\[0]=((int)(v\[0]));...

\\\* code/client/cl\\\_cgame.c: CG\\\_SNAPVECTOR.
\\\* code/server/sv\\\_game.c:  G\\\_SNAPVECTOR.
Note: these go through trap\\\_SnapVector in syscalls.

\\\\\\\* code/unix/unix\\\\\\\_shared.c (Sys\\\\\\\_SnapVector): sticking to
	old Linux version for now...
	\\\\\\\* code/win32/win\\\\\\\_shared.c (Sys\\\\\\\_SnapVector): changed.
	Note: Graeme points out this was changed to fix ftol
	artifacts?
	TODO: calculate errors for various ftol variants...

	\\\\\\\* code/qcommon/vm\\\\\\\_x86.c: both the old fistp code (1.17)
	and the new qftol function apparatently work. Using the
	ftol.nasm code for now.

	\\\\\\\* code/unix/Makefile: DO\\\\\\\_NASM and ftol.o. 

	\\\\\\\* code/unix/ftol.nasm (qftol): created from Mike's SoF
	replacements, with Andrew's help to satify the VM
	stack/call requirements.
	TODO: use Q\\\\\\\_ftol herein to replace myftol elsewhere.

	\\\\\\\* code/unix/unix\\\\\\\_main.c (Sys\\\\\\\_ConfigureFPU): SIGFPE. 
	TODO: divide by zero in botlib. Disable this for now.
	Note: we can't introduce calculation differences between
	versions, so fixing these will have to wait.

	\\\\\\\* code/qcommon/vm\\\\\\\_x86.c: two new lines in Win32 branch 
	missing from Linux assembly in AsmCall:
	 mov eax, dword ptr \\\\\\\[edi] 
	 and eax, \\\\\\\[callMask]      
        Added, doesn't seem to affect UI etc. bugs.
	Later: no FTOL\\\\\\\_PTR, use fistp non-IEEE assembly as in old
	version. This seems to work for Q3 and TA, while qftol 
	(simple cast) does not - for Win32 Graeme says the reverse 
	is true.

	\\\\\\\* code/qcommon/vm\\\\\\\_x86\\\\\\\_old.c: used the old cvs-1.17 version.
	Two fixes (Hunk\\\\\\\_Alloc, Com\\\\\\\_Memcpy), and it works:
	  +set vm\\\\\\\_game 2 +set vm\\\\\\\_ui 2 +set vm\\\\\\\_cgame 2 
        UI, cgame and game w/o apparent problems.










### 2000-12-12  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/unix/Makefile: cleanup of redundant flags.
Removed bogus MALLOC\_CHECK (note to self: export MALLOC\_CHECK\_=2).  
Also DO\_SHLIB\_CC on all UI DLL's.
Added and removed DEBUG\_VM flag.
TODO: figure out whether Zoid did UI this way intentionally.
Note: this seemingly fixed the botimport problem, although
most of the changes were just redundant CFLAGS removed. Given
our wanker toolchain, should have been more paranoid. All
DLL's can now be used w/o apparent problems.

\\\* code/server/sv\\\_main.c: gvm init.
\\\* code/server/sv\\\_game.c: gvm assertions.
\\\* code/unix/unix\\\_main.c (Sys\\\_LoadDll): print vmMain
Note: top no avail. There is some odd ld/gdb problem here
that prevents examining globals and obfuscates part of
the stack between VM\\\_Call and lower level code, through
G\\\_InitGame. This is not just DLL's being loaded and unloaded.
Wromg flags during build? The vmCvar for "bot\\\_developer"
ends up overlapping global botimport in memory, which
thus zero-fills part of the function pointer table.

\\\\\\\* code/server/sv\\\\\\\_bot.c (SV\\\\\\\_BotInitBotLib): this (by way of
	GetBotLibAPI) is responsible for setting botimport, which,
	if using the game DLL, is not properly set up. Called in
	SV\\\\\\\_Init().

	\\\\\\\* code/game/q\\\\\\\_shared.c: Q\\\\\\\_strncpyz does zero padding (duh).
	Note: calls strncpy, which does a zero fill up to destsize.
	If destsize exceeds memory size, zero padding will overwrite
	adjacent memory. Suspicion was this happened to botimport.

	\\\\\\\* code/qcommon/cvar.c: possible problem in Q\\\\\\\_strncpyz call.

	\\\\\\\* code/botlib/be\\\\\\\_ai\\\\\\\_weap.c (weaponinfo\\\\\\\_fields): made this static.
	Note: it seems that the "number" string got replaced by
	 p def.fields\\\\\\\[0]
         {name = 0x40000000 "\\\\\\\\177ELF\\\\\\\\001\\\\\\\\001\\\\\\\\001", offset = 2, type = 50, ..
        Memory corruption?

	\\\\\\\* code/game/inv.h (WEAPONINDEX\\\\\\\_GAUNTLET): defined here. 
	\\\\\\\* botfiles/weapons.c (Gauntlet): the baseq3/qagamei386.so parser
	breaks here:
	 number				WEAPONINDEX\\\\\\\_GAUNTLET
	\\\\\\\* code/botlib/l\\\\\\\_precomp.c (SourceWarning): added assertion to
	trap botlib parsing problem..

	\\\\\\\* RC1: for beta test. Using my own vm/ui.qvm files in this case.
	TODO: Setup with nouninstall.
	TODO: fix game DLL/ botlib setup problem (so all DLL's work)
	TODO: SIGFPE
	TODO: profile?
	
	\\\\\\\* code/unix/Makefile (ai\\\\\\\_vcmd.o): added to game DLL linkage. 
	How the fuck did this happen?
	DONE: "qagamei386.so: undefined symbol: BotVoiceChat\\\\\\\_Defend"

	\\\\\\\* TEST:  +set vm\\\\\\\_ui 2 (vm\\\\\\\_x86, not interpreter). Breaks!
	Further: qagame had undefined, but seemingly gets reloaded 
	second try (I hate the Linux linker).
	\\\\\\\* TODO: never reload fail DLL, abort engine





















### 2000-12-11  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* TEST: recompile QVM/DLL and executable to test new UI code.
The UI QVMs from the paks still do not work.

\\\* SOS: changes in UI code!
\\\* code/q3\\\_ui/ui\\\_public.h: this file is deprecated
Note: e.g. it does not contain the background track calls.
\\\* code/ui/ui\\\_public.h: the uiImport\\\_t enum here determines
the values.
\\\* code/ui/ui\\\_syscalls.asm: same as q3\\\_ui now, were:
equ floor					-111
equ ceil					-112
\\\* code/q3\\\_ui/ui\\\_syscalls.asm: these are now switched, were:
equ trap\\\_S\\\_StartBackgroundTrack			-63
equ trap\\\_S\\\_StopBackgroundTrack				-64
The new values match the ui/ equivalent. Also, floor (-108)
and ceil (-109) are different in ui/.

\\\\\\\* CVS: going to check in this snapshot and tag it as
	    cvs tag id1-27g-loki001209-rc4
	Presumed equivalent to SOS tag "1.27g RC4" (master). As I can't
	obtain the tagged code using SOS (neither Win32 nor Linux client)
	I can only guess.

	\\\\\\\* TEST: use my own VM code, ion baseq3/vm/\\\\\\\*.qvm and missionpack/vm/.
	This works - in other words, the menu bug seems in the UI code, and
	is fixed in my codebase.

	\\\\\\\* TEST: make release. 
	Note: I can postpone DLL specific problems. Bad performance is not
	as important as outright bugs. Thus the UI QVM issue is the only
	one that stops me from creating an RC.
	TODO: Q3 UI QVM code from pak file does not work (neither does TA).
	TODO: sound with video playback still awful. Threaded sound, I guess.
	TODO: ERROR: couldn't open demos/DEMO002.dm3.dm\\\\\\\_48 (same demo001.dm3.dm\\\\\\\_48)
	
	TODO: do not show Q3 demos in TA menu?
	TODO: new demos for Q3? Or at least error message?
	
	\\\\\\\* code/game/bg\\\\\\\_lib.c: itrinsics excluded by Q3\\\\\\\_VM (another -O
	compile). Uninitialized variable.
	\\\\\\\* code/unix/Makefile: -O for uninit on patched code. Also shortcuts. 
	TODO: DC\\\\\\\_ONLY seems an obsolete flag, used in Makefiles, not source.

	\\\\\\\* TEST: +set sv\\\\\\\_pure 0 +set vm\\\\\\\_game 1 +set vm\\\\\\\_cgame 1 +set vm\\\\\\\_ui 0
	Turns out that the pak0.pk3 UI QVM code is seemingly broken in TA
	and Q3, but my UI DLL is not. In reverse, the QVM game/cgame for
	Q3 seems to work quite well (including bots). The TA game/cgame
	also works, including botlib init.
	TODO: BotLib Init using game DLL gives: 
	TODO:  Error: file weapons.c, line 38: unknown structure field number
        TODO:  Fatal: couldn't load the weapon config
        TODO:  Error: BotLoadMap: bot library used before being setup
	
	\\\\\\\* TEST: checked the rc4winstlr.zip CD tree against
	my test install. baseq3/pak4.pl3 and missionpack/pak0.pk3
	are identical, but I finally recognized that there was
	a missionpack/pak1.pk3 not in the final install - left over 
	from an earlier update from id. Doesn't seem to affect the
	DLL based runs at all.
	Note: I still do not have the final CD snapshot Robert
	promised me mid last week, they haven't even fixed the
	FTP account they took down. Communication with id is as
	abyssmal as ever. 










### 2000-12-08  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* TEST: running with RC4 data files.
TODO: "bot library used before setup" (Q3+TA)
TODO: Q3 old mods wreak havoc (graceful bounce)
TODO: suppress "FreeType code not available" in renderer
TODO: can't move in Q3
TODO: items flicker in Q3
TODO: no decals in Q3
TODO: VM UI code still broken (Q3+TA)
TODO: sound code is awful
TODO: video playback inferior to earlier builds

\\\* code/q3\\\_ui/ui\\\_local.h: prototype trap\\\_VerifyCDKey(..)
\\\* code/game/g\\\_active.c ( StuckInOtherClient): TA only.
\\\* code/cgame/cg\\\_draw.c: 4x unbalanced `#endif' - from patch?
\\\* code/null/null\\\_client.c (CL\\\_CDKeyValidate): dummy added.
\\\* code/qcommon/common.c: Q\\\_acos missing, changed conditionals

\\\\\\\* code/qcommon/vm\\\\\\\_x86.c: unreacheable \\\\\\\_asm instruction that
	gcc doesn't quite like... #if 0'ed for now
 	TODO: understand \\\\\\\_asm { mov eax,\\\\\\\[ebx] }, fix it for gcc

	\\\\\\\* TEST: compile...

	\\\\\\\* code/ui/ui\\\\\\\_main.c: full REJECT. Manual merge.
	Note: preserved debug\\\\\\\_protocol lines, who knows what it's good for.

	\\\\\\\* code/qcommon/files.c: REJECT. SafeMode, demo server FS\\\\\\\_Restart.

	\\\\\\\* code/client/snd\\\\\\\_mem.c: REJECT: $SOS$.
	\\\\\\\* code/client/snd\\\\\\\_dma.c: REJECT: $SOS$.
	\\\\\\\* code/client/cl\\\\\\\_cin.c: REJECT. com\\\\\\\_timescale, $SOS$.

	\\\\\\\* code/cgame/cg\\\\\\\_draw.c: REJECT. Lots, but virtually all either
	float postfix (on some, not all places), or #ifndef MISSIONPACK
	that I had already put in during -Werror (conditional unused).

	\\\\\\\* code/cgame/cg\\\\\\\_consolecmds.c: REJECT. id commented unused code
	that I had #if 0'ed earlier.

	\\\\\\\* code/game/: three REJECT for $SOS$.
	\\\\\\\* code/botlib/: lots REJECT for $SOS$.

	\\\\\\\* Patch: patching up from demo source.
	ln -s sos001204-rc4 work
 	diff -urbB sos001122-demo/ work > work.diff
 	ln -s cvs-1.27b/ work
 	patch -p0 \< work.diff  > work.patch
 	find cvs1.27b/ -name '\\\\\\\*.rej' -print

	\\\\\\\* CVS: going to check in this snapshot and tag it as
	    cvs tag id1-27b-loki001208-demo
	Then patching up to RC4, as of sos001204-rc4 (no changes since,
	should be equivalent to SOS tag "1.27g RC4" (raduffy), i.e. master.

	\\\\\\\* TEST: installed demota/ from Win32 distribution. Binary
	fails claiming "Corrupted pak0.pk3". Abandoned.
	Note: a Linux demo for Q3TA has no priority. Most important is
	the Q3A point release in time for Q3TA hitting shelves, followed
	by testing for Q3TA. The source is in CVS and tagged (see above)
	in case a demo matching the released files has to be provided
	later.
	




















### 2000-12-07  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* TEST: compile and link - succeeds.

\\\* code/ui/ui\\\_main.c: UI\\\_StopServerRefresh now uaws.
New unused variables.

\\\\\\\* code/unix/unix\\\\\\\_main.c: added  Sys\\\\\\\_LowPhysicalMemory() stub.
	TODO: write Linux equivalent to GlobalMemoryStatus.

	\\\\\\\* code/qcommon/common.c: Com\\\\\\\_Memset/Com\\\\\\\_Memcpy. Neither assembly 
	nor C versions included if not on Win32 i386. 
	TODO: using/porting assembly?

	\\\\\\\* code/qcommon/files.c: unused variable.
	TODO: fs\\\\\\\_scrambledProductId unused if 0 for now.
	Note: -DFS\\\\\\\_MISSING for id's pak cleanup, not used.

	\\\\\\\* TEST: compile and link - fails.

	\\\\\\\* code/macosx/Client/Makefile.postamble: empty ORIG.
	\\\\\\\* code/macosx/Client/Makefile.preamble: ORIG. $(BOTLIB\\\\\\\_OBJS) added.

	\\\\\\\* code/server/sv\\\\\\\_client.c: ORIG. Com\\\\\\\_Memset.
	\\\\\\\* code/renderer/tr\\\\\\\_shader.c: ORIG. Com\\\\\\\_Memset, CIN\\\\\\\_Shader.
	\\\\\\\* code/qcommon/vm\\\\\\\_x86.c:  ORIG. Com\\\\\\\_Memcpy. 
	\\\\\\\* code/qcommon/unzip.c: REJECT. Com\\\\\\\_Memcpy, $SOS$. 
	\\\\\\\* code/qcommon/qcommon.h: ORIG. PROTOCOL 47, plus Sys\\\\\\\_LowPhysicalMemory.
	\\\\\\\* code/qcommon/md4.c: Com\\\\\\\_Memset,Com\\\\\\\_Memcpy (ORIG).
	\\\\\\\* code/qcommon/files.c (Sys\\\\\\\_ConcatenateFileList): REJECT.
	Our additons threw it off, plus $SOS$. 
	\\\\\\\* code/qcommon/common.c: they fixed same unused variables (REJECT).

	\\\\\\\* code/ui/ui\\\\\\\_shared.c: additions (ORIG).
	\\\\\\\* code/ui/ui\\\\\\\_gameinfo.c: COM\\\\\\\_Compress added (ORIG).
	\\\\\\\* code/ui/ui\\\\\\\_atoms.c: print statements removed (ORIG).
	\\\\\\\* code/ui/ui\\\\\\\_main.c (UI\\\\\\\_DoServerRefresh): REJECT on comment edit... 

	\\\\\\\* code/game/g\\\\\\\_cmds.c (Cmd\\\\\\\_VoiceTaunt\\\\\\\_f): logic changed heavily. ORIG.
	\\\\\\\* code/game/q\\\\\\\_shared.h: Q3\\\\\\\_VERSION "Q3 Team Arena Demo 1.27b"
	plus Com\\\\\\\_Memset, Com\\\\\\\_Memcpy, CIN\\\\\\\_shader, COM\\\\\\\_Compress.
	\\\\\\\* code/game/g\\\\\\\_main.c: Cvar change only
	\\\\\\\* code/game/ai\\\\\\\_dmq3.c: $SOS$.

	\\\\\\\* code/client/snd\\\\\\\_mix.c: Com\\\\\\\_Memset
	\\\\\\\* code/client/client.h: additions (ORIG).
	\\\\\\\* code/client/snd\\\\\\\_mem.c: see below.
	\\\\\\\* code/client/snd\\\\\\\_dma.c: $SOS$ (CVS keyword).

	\\\\\\\* code/client/cl\\\\\\\_cin.c: they removed unused (REJECT).
	\\\\\\\* code/cgame/cg\\\\\\\_servercmds.c: ORIG. compress, noTaunt etc.
	\\\\\\\* code/cgame/cg\\\\\\\_main.c: ORIG. Conditonal branch, COM\\\\\\\_Compress.
	\\\\\\\* code/cgame/cg\\\\\\\_consolecmds.c: ORIG. Cvar values changed.
	\\\\\\\* code/cgame/cg\\\\\\\_draw.c (CG\\\\\\\_DrawTeamBackground): ORIG. 
	no reject but \\\\\\\*.orig file created. I just mark spots were 
	code changed after verifying the patch succeeded.

	\\\\\\\* code/cgame/cg\\\\\\\_event.c: fixed reject (REJECT).
	\\\\\\\* code/botlib/: all \\\\\\\*.rej here due to SOS/CVS $Keyword$.
	TODO: preserve SOS comments/rev history somehow.

	\\\\\\\* Patch: patching up to demo source.
	ln -s sos001122-demo work
 	diff -urbB sos001119/ work > work.diff
 	ln -s cvs-1.26/ work
 	patch -p0 \< work.diff  > work.patch
 	find cvs1.26/ -name '\\\\\\\*.rej' -print           
	
	\\\\\\\* CVS: going to check in this snapshot and tag it as
	  cvs tag id1-26w-loki001207
	to prepare for upgrading to RC4. I have already made
	many more changes than I wanted to w/o getting any 
	closer to pinpointing the problem, I might as well
	patch up to id's more current sources.

	\\\\\\\* code/botlib/be\\\\\\\_interface.c: initialize by memset. Turns
	out that this fails in Export\\\\\\\_BotLibSetup on BotSetupWeaponAI
	loading "weapons.c" (from the pak, presumably) with an unknown
	structure field number. Mismatch of datafiles vs. source again.
	
	TODO: id replaced memsets in later source.
	TODO: have memsets on all exports and imports.

	\\\\\\\* SOS: RC4 source should be tagged "1.27g RC4" (raduffy).
	Unfortunately the Linux client doesn't care a bit. Show
	History does work if from/to date differ by at least a
	day, and it shows the tag on code/ (only that subtree),
	but recursive get aborts halfway.
	Manual: http://www.sourcegear.com/SOS/Doc/










### 2000-12-06  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* TEST: accepting missing shaders now. No bots, but I can
actually enter the game and play (more than can be said for
classic Q3 right now).
TODO: Error: BotStartFrame: bot library used before being setup

\\\* code/renderer/tr\\\_shader.c: took out assertion for now...
\\\* TEST: now missiopack/cgame loads
TODO: tr\\\_shader.c:2275: R\\\_FindShaderByName: failed
TODO: searches ui/assets/3\\\_cursor2.TGA, has ui/assets/3\\\_cursor3.tga

\\\\\\\* code/unix/Makefile (MPCGOBJ): ui\\\\\\\_shared.o (duh).
	DONE: /cgamei386.so: undefined symbol: PC\\\\\\\_Float\\\\\\\_Parse
	
	\\\\\\\* code/botlib/be\\\\\\\_ai\\\\\\\_goal.c: initialize campspots etc. This
	might or might not fix this one (didn't get back to gdb due
	to mouse-only navigation).
	DONE: 0x80d1d5b in BotFreeInfoEntities () at be\\\\\\\_ai\\\\\\\_goal.c:447	

	\\\\\\\* TEST: this time with missionpack/cgame loading... noy
	TODO: TA menu blocked after end of intro movie
	TODO: console in\\\\\\\_mouse 1 doesn't grap pointer even on vid\\\\\\\_start?

	\\\\\\\* code/cgame/cg\\\\\\\_newdraw.c: -Werror.
	\\\\\\\* code/unix/Makefile (MPCGOBJ): cg\\\\\\\_newdraw.o was missing (duh).
	DONE: missionpack/cgamei386.so: undefined symbol: CG\\\\\\\_OwnerDrawVisible"

	\\\\\\\* code/ui/ui\\\\\\\_shared.c:1309 assign after bail on NULL.
	DONE: segfault in Item\\\\\\\_SetFocus (item=0x0, x=0, y=0)

	\\\\\\\* TEST: new set of DLL's (this time hopefully correct).
	All baseq3/ DLL's load, as does the missionpack/ UI DLL.
	The menus now work in both (TA seems mouse-only on everything 
	but "Quit"). Segfault on delayed TA "Quit" (stack fubared):
	#5  0x809fc28 in VM\\\\\\\_Call (vm=0x88408a0, callnum=3) at ..//qcommon/vm.c:617
	#6  0x805aafc in CL\\\\\\\_KeyEvent (key=9, down=qtrue, time=128644) cl\\\\\\\_keys.c:1194
	TODO: TA menu's w/o mouse? 
	TODO: Win32 goes submenus but does not unfold
	TODO: Linux does not go submenus
	
	\\\\\\\* code/ui/ui\\\\\\\_main.c: see below. 
	TODO: LCC gets fits -  operands of = have illegal types 
	TODO: 'pointer to const unsigned char' and 'pointer to const char'
	\\\\\\\* code/ui/ui\\\\\\\_shared.c: see below.
	\\\\\\\* code/ui/ui\\\\\\\_gameinfo.c: see below.
	\\\\\\\* code/ui/ui\\\\\\\_atoms.c: see below.
	\\\\\\\* code/game/g\\\\\\\_bot.c: more cruft.
	\\\\\\\* code/cgame/cg\\\\\\\_draw.c: loads of functions modified for
	MISSIONPACK that aren't used at all for MISSIONPACK anymore.
	Development relics.

	\\\\\\\* code/cgame/cg\\\\\\\_consolecmds.c: -Werror.
	Note: due to Makefile error never ever compiled...

	\\\\\\\* code/unix/Makefile: fixed various dependency errors
	for game and ui library.
	TODO: create a new Makefile with patsubst and rules.
	TODO: why C\\\\\\\_ONLY in the i386 dedicated server?

	\\\\\\\* code/unix/unix\\\\\\\_main.c: use dlerror() excessively.
	Littered more unused DLL related functions with assert(0).
	TODO: clean up Sys\\\\\\\_Load/UnloadDll (a real mess)
	TODO: remove Zoid code cruft (unused per-DLL functions)
	
	\\\\\\\* code/game/bg\\\\\\\_misc.c: changed G\\\\\\\_Printf for Com\\\\\\\_Printf.
	This was undefined in baseq3/uii386.so preventing loading.

	\\\\\\\* TEST: +set sv\\\\\\\_pure 0 +set vm\\\\\\\_game 0 +set vm\\\\\\\_cgame 0 +set vm\\\\\\\_ui 0
	Note: so far I used only the game DLL..  duh.
	UI DLL fails to load: missing G\\\\\\\_Printf.

	\\\\\\\* code/unix/Makefile:  -DMALLOC\\\\\\\_CHECK in addition to
	the -DZONE\\\\\\\_DEBUG I have used since switching to calloc.
	Using MALLOC\\\\\\\_CHECK=1 for now, might use 2 if something
	comes up.

	\\\\\\\* code/renderer/tr\\\\\\\_init.c (GL\\\\\\\_SetDefaultState): it does get 
	called, but does not show up in the log.
	
	\\\\\\\* TEST: tried executing a script - get bounced.
	TODO: is there any way to jump into a map?
	TODO: cl\\\\\\\_cinematics 0 (suppress all fullscreen RoQ)
	Next: used r\\\\\\\_logfile 200 in Win32 (RC4) and Linux.
	There is a buckload of setup code seemingly not done
	at all in Linux? Either that, or logging is enabled
	with a delay in Linux.

	\\\\\\\* code/unix/linux\\\\\\\_glimp.c: fixed autorepeat (H2/Fakk2 way). 










### 2000-12-05  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/renderer/tr\_mesh.c: added assert there.
\* TEST: menus and in-game drawing are just as they were with
the initial SOS001119 port. In addition:
R\_AddMD3Surfaces: no such frame 0 to -2147483477
for 'models/players/xaero/upper.md3'
R\_AddMD3Surfaces: no such frame -2147483477 to 171
R\_AddMD3Surfaces: no such frame 171 to -2147483498
ad nauseam (used as my player model).
Triggered: haveing a trRefEntity\_t \*) 0x41dbbd00 with
frame = -2147483477. Might be a red herring (PRINT\_DEVELOPER),
ignore for now.

\\\* code/ui/ui\\\_main.c: missing return.
\\\* code/ui/ui\\\_shared.c: excess byte in initializer (which gcc
did not caught, but LCC did). Also LCC complains about
missing returns, but gcc doesn't (neither says unreacheable
code though). If necessary (MsVC?) guard with Q3\\\_VM.

\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_ingame.c: see below.
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_atoms.c: voidfunc\\\\\\\_f. LCC warns about conversion 
	from `pointer to void' to `pointer to void function(void)' 
	being compiler dependent. Casting NULL. Guess what, doesn't fix 
	it either.
	TODO: do not use these cursed scripts to generate VM code,
	we do not have proper rules for LCC/q3asm, thus the files never
	get updated.

	\\\\\\\* code/unix/Makefile: for paranoia's sake recreated the 1.17
	compile for the UI DLL (where only q\\\\\\\_shared/math were actually
	compiled as DO\\\\\\\_SHLIB\\\\\\\_CC.
	Later: switched to different gcc. 

	\\\\\\\* STATIC: remaining problems are vmMain (same entry point for all
	DLL's), could use cgMain, uiMain and gMain here for HARD\\\\\\\_LINKED. 
	Note: I don't think id has used this in ages.
	Plus all the collisions in \\\\\\\*\\\\\\\_syscalls.c, which simply can't be
	fixed cheaply. None is the superset of 2 others, neither seems
	w/o overlap to others. Full stop.

	\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_move.c: see below.
	\\\\\\\* code/game/ai\\\\\\\_dmq3.c: VEC\\\\\\\_UP/DOWN, MOVEDIR\\\\\\\_UP/DOWN now static.
	See also game/g\\\\\\\_utils.c for existing static duplicates.

	\\\\\\\* code/game/q\\\\\\\_shared.h: #define stricmp strcasecmp 
	\\\\\\\* code/unix/Makefile:  no mo'  -Dstricmp=strcasecmp, see q\\\\\\\_shared.h
	Also: no mo'  -I/usr/include/glide, no FX
	TODO: are we building against system GL headers? ../Mesa/?

	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_atoms.c: comment on duplication
	\\\\\\\* code/cgame/cg\\\\\\\_drawtools.c: use UI/CGAME\\\\\\\_HARD\\\\\\\_LINKED on UI duplicates 
	TODO: does this UI\\\\\\\_ code in cg\\\\\\\_drawtools/ui\\\\\\\_atoms belong into ui\\\\\\\_shared?

	\\\\\\\* code/unix/Makefile: use -DQ3\\\\\\\_STATIC 
	\\\\\\\* code/game/q\\\\\\\_shared.h (\\\\\\\*\\\\\\\_HARD\\\\\\\_LINKED): trigger on Q3\\\\\\\_STATIC 
	Later: collision between UI and CGAME is still there. This fixed
	the Com\\\\\\\_Error, Com\\\\\\\_Printf issues though

	\\\\\\\* code/unix/Makefile ($(B)/q3static/ai\\\\\\\_vcmd.o): this file was
	missing, hence undefined symbol.
	($(B)/baseq3/game/ai\\\\\\\_vcmd.o): same here.
	($(B)/missionpack/game/ai\\\\\\\_vcmd.o): same here.

	\\\\\\\* STATIC: cg\\\\\\\_syscalls.c, g\\\\\\\_syscalls.c and ui\\\\\\\_syscalls.c alias.
	Multiply defined symbols:
	 Com\\\\\\\_Error, Com\\\\\\\_Printf
         VEC\\\\\\\_UP, VEC\\\\\\\_DOWN
	 MOVEDIR\\\\\\\_UP, MOVEDIR\\\\\\\_DOWN
	 vmMain
	 dllEntry
	 PASSFLOAT
	 trap\\\\\\\_Error
	 trap\\\\\\\_Milliseconds
	 trap\\\\\\\_Argc
	 trap\\\\\\\_Argv
         trap\\\\\\\_FS\\\\\\\_FOpenFile
	 trap\\\\\\\_FS\\\\\\\_Read
	 trap\\\\\\\_FS\\\\\\\_Write
         trap\\\\\\\_FS\\\\\\\_FCloseFile
         trap\\\\\\\_FS\\\\\\\_GetFileList
	 trap\\\\\\\_R\\\\\\\_RegisterModel
	 trap\\\\\\\_R\\\\\\\_RegisterSkin
	 trap\\\\\\\_R\\\\\\\_RegisterFont
	 trap\\\\\\\_R\\\\\\\_RegisterShaderNoMip
	 trap\\\\\\\_R\\\\\\\_ClearScene
	 trap\\\\\\\_R\\\\\\\_AddRefEntityToScene
	 trap\\\\\\\_R\\\\\\\_AddPolyToScene
         trap\\\\\\\_R\\\\\\\_AddLightToScene
	 trap\\\\\\\_R\\\\\\\_RenderScene
	 trap\\\\\\\_R\\\\\\\_SetColor
         trap\\\\\\\_R\\\\\\\_DrawStretchPic
	 trap\\\\\\\_R\\\\\\\_ModelBounds
	 trap\\\\\\\_UpdateScree
         trap\\\\\\\_S\\\\\\\_StartLocalSound
	 trap\\\\\\\_S\\\\\\\_RegisterSound
	 trap\\\\\\\_Key\\\\\\\_IsDown
	 trap\\\\\\\_Key\\\\\\\_GetCatcher
	 trap\\\\\\\_Key\\\\\\\_SetCatcher
	 trap\\\\\\\_GetGlconfig
         trap\\\\\\\_PC\\\\\\\_AddGlobalDefine
	 trap\\\\\\\_PC\\\\\\\_LoadSource
	 trap\\\\\\\_PC\\\\\\\_FreeSource
	 trap\\\\\\\_PC\\\\\\\_FreeSource
	 trap\\\\\\\_PC\\\\\\\_ReadToken
	 trap\\\\\\\_PC\\\\\\\_SourceFileAndLine
	 trap\\\\\\\_S\\\\\\\_StopBackgroundTrack
	 trap\\\\\\\_S\\\\\\\_StartBackgroundTrack
	 trap\\\\\\\_RealTime
	 trap\\\\\\\_CIN\\\\\\\_PlayCinematic
	 trap\\\\\\\_CIN\\\\\\\_StopCinematic
	 trap\\\\\\\_CIN\\\\\\\_RunCinematic
	 trap\\\\\\\_CIN\\\\\\\_DrawCinematic
         trap\\\\\\\_CIN\\\\\\\_SetExtents
	 trap\\\\\\\_MemoryRemaining
         trap\\\\\\\_SendConsoleCommand
	 trap\\\\\\\_Cvar\\\\\\\_Register
	 trap\\\\\\\_Cvar\\\\\\\_Update
         trap\\\\\\\_Cvar\\\\\\\_Set
  	 trap\\\\\\\_Cvar\\\\\\\_VariableValue
         trap\\\\\\\_Cvar\\\\\\\_VariableStringBuffer
	 trap\\\\\\\_RealTime
	 trap\\\\\\\_SnapVector  // used in game/bg\\\\\\\_\\\\\\\*.c, needs conditional
	More aliasing between ui\\\\\\\_atoms.c and cg\\\\\\\_drawtools.c:
         UI\\\\\\\_DrawBannerString
         UI\\\\\\\_ProportionalStringWidth
	 UI\\\\\\\_ProportionalSizeScale
        Undefined symbol: ai\\\\\\\_team.o: In function `FindHumanTeamLeader':
         ai\\\\\\\_team.c:1899: undefined reference to `BotVoiceChat\\\\\\\_Defend'
	Note: 
	
	\\\\\\\* code/game/g\\\\\\\_main.c: unused.
	\\\\\\\* code/game/g\\\\\\\_arenas.c: unused.
	\\\\\\\* code/game/ai\\\\\\\_team.c: init.
	\\\\\\\* code/game/ai\\\\\\\_dmnet.c: /\\\\\\\* in comment (odd).
	Note: why do these come up now but not earlier?
	TODO: the make dependencies might target wrong files.

	\\\\\\\* code/unix/Makefile (TARGETS): added q3static.
	Note: this is baseq3/

	\\\\\\\* TEST: +set r\\\\\\\_logfile 100. It seems that the addition of
	code (add an assertion etc.) changes the behavio of the binary.
	The intro cinematics code seems to suffer first - didn't play,
	then played, then (another assert added) doesn't play. Watch
	out for (missionpack):
	  UI\\\\\\\_CIN\\\\\\\_PlayCinematic
          SCR\\\\\\\_PlayCinematic( mpintro.roq )
          trFMV::play(), playing mpintro.roq
	Also fails to exit cleanly: break gives
	 #0  0x401919ee in \\\\\\\_\\\\\\\_select ()
         #1  0x400bbcb8 in \\\\\\\_\\\\\\\_DTOR\\\\\\\_END\\\\\\\_\\\\\\\_ ()
         #2  0x4004baa1 in \\\\\\\_XSend ()
         #3  0x452b009f in GLXRenderFlush ()
         #4  0x804ce0c in \\\\\\\_XRead ()
         #5  0x40680813 in ?? ()
	Stack is corrupted.
        Note: \\\\\\\~/.q3a/gl.log
	TODO: write per-frame files (see Heretic2)
	TODO: add Heretic2 QGL (more detail)

	\\\\\\\* code/unix/linux\\\\\\\_qgl.c (QGL\\\\\\\_EnableLogging): fixed countdown
	(i.e. propagated changes from win32/, see Fakk2).

	\\\\\\\* code/unix/linux\\\\\\\_glimp.c: fixed QGL\\\\\\\_EnableLogging argument
	to avoid cast error (always qfalse).

	\\\\\\\* code/unix/Makefile (DEBUG\\\\\\\_CFLAGS): use ZONE\\\\\\\_DEBUG.

	\\\\\\\* code/qcommon/common.c: replaced malloc with calloc calls.

	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_local.h: have to use ui/ui\\\\\\\_public.h
	\\\\\\\* code/cgame/cg\\\\\\\_servercmds.c: requires ../ui/menudef.h

	\\\\\\\* code/cgame/cg\\\\\\\_consolecmds.c: ui/ui\\\\\\\_shared.h is unique.
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_public.h: make sure this won't be compiled.	
	\\\\\\\* code/client/client.h: we have to include ui/ui\\\\\\\_public.h.
	Note: id is obviously maintaing only the ui/ headers, so the
	headers in q3\\\\\\\_ui/ are deprecated.

	\\\\\\\* code/renderer/tr\\\\\\\_shader.c: added assertions (see Ryan's Fakk2
	problems with missing shaders).

	\\\\\\\* code/game/g\\\\\\\_cmds.c: below.
	\\\\\\\* code/game/ai\\\\\\\_vcmd.c: below.
	\\\\\\\* code/game/ai\\\\\\\_team.c: below.
	\\\\\\\* code/game/ai\\\\\\\_dmnet.c: below.
	\\\\\\\* code/game/ai\\\\\\\_dmq3.c: below.
	\\\\\\\* code/game/ai\\\\\\\_chat.c: below.
	\\\\\\\* code/game/ai\\\\\\\_cmd.c: ../../ui/menudef.h (new Q3TA script directory).

	\\\\\\\* code/cgame/cg\\\\\\\_newdraw.c: make sure it won't compile w/o MISSIONPACK.

	\\\\\\\* code/cgame/cg\\\\\\\_servercmds.c: below.
	\\\\\\\* code/cgame/cg\\\\\\\_event.c: below.
	\\\\\\\* code/cgame/cg\\\\\\\_consolecmds.c: below.
	\\\\\\\* code/client/keys.h: below.
	\\\\\\\* code/client/client.h: below.
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_local.h: include from ../q3\\\\\\\_ui/ not ../ui/.
	Note: id seems to intentionally use the header from the new ui/.

	\\\\\\\* Makefile: checked -I$(UIDIR), there is no such. That means all
	files include directly, which means all (including Q3) are using
	the new ui/ headers.










### 2000-12-04  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* RC4: released as 362101115 Dec  4 11:40 TA\_Q3A\_RC4.zip

\\\* TEST: the corrupted menu problem is back :-(. Looks like I am in
for a static link next.

\\\\\\\* code/unix/Makefile (clean2): fixed (not all new OBJ covered).
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_teamorders.c: -Werror.
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_team.c: -Werror. 
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_qmenu.c (Bitmap\\\\\\\_Draw): -Werror. 
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_mods.c (UI\\\\\\\_Mods\\\\\\\_LoadModsFromFile): unused. -Werror.
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_controls2.c: -Werror.
	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_atoms.c: -Werror
	\\\\\\\* code/null/null\\\\\\\_client.c: -Werror.
	\\\\\\\* code/unix/linux\\\\\\\_joystick.c: -Werror.
	\\\\\\\* code/unix/linux\\\\\\\_glimp.c: -Werror. 
	\\\\\\\* code/unix/linux\\\\\\\_qgl.c: -Werror. 
	\\\\\\\* code/unix/unix\\\\\\\_shared.c: -Werror. 
	\\\\\\\* code/unix/unix\\\\\\\_net.c: -Werror.
	\\\\\\\* code/unix/linux\\\\\\\_local.h: added missing prototypes.
	\\\\\\\* code/unix/unix\\\\\\\_main.c: -Werror. Includes linux\\\\\\\_local.h
	\\\\\\\* code/jpeg-6/jdmainct.c: see below.
	\\\\\\\* code/jpeg-6/jcmainct.c: variables called "main" (\\\\\\\*moan\\\\\\\*) 
	\\\\\\\* code/jpeg-6/jcdctmgr.c (forward\\\\\\\_DCT): -Werror.
	\\\\\\\* code/botlib/l\\\\\\\_script.c (PS\\\\\\\_ReadLiteral): -Werror
	\\\\\\\* code/botlib/l\\\\\\\_precomp.c (PC\\\\\\\_AddBuiltinDefines): -Werror.
	\\\\\\\* code/botlib/be\\\\\\\_interface.c: -Werror.
	\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_reach.c: -Werror
	\\\\\\\* code/botlib/be\\\\\\\_aas\\\\\\\_cluster.c: -Werror 
	\\\\\\\* code/game/be\\\\\\\_aas.h: -Werror. 
	Note: MrElusive accumulates a lot of code history in nested comments,
	which gcc doesn't like at all. #if 0'ed to avoid.
	\\\\\\\* code/qcommon/vm\\\\\\\_interpreted.c: -Werror.
	\\\\\\\* code/qcommon/unzip.c: -Werror.
	\\\\\\\* code/cgame/cg\\\\\\\_servercmds.c: -Werror.
	\\\\\\\* code/cgame/cg\\\\\\\_main.c: -Werror.
	\\\\\\\* code/cgame/cg\\\\\\\_drawtools.c: -Werror.
	\\\\\\\* code/game/bg\\\\\\\_misc.c: -Werror.
	\\\\\\\* code/game/be\\\\\\\_ai\\\\\\\_move.h (bot\\\\\\\_avoidspot\\\\\\\_s): added.
	\\\\\\\* code/botlib/be\\\\\\\_ai\\\\\\\_move.c: removed typedef struct bot\\\\\\\_avoidspot\\\\\\\_s
	\\\\\\\* code/client/snd\\\\\\\_mix.c: -Werror.
	\\\\\\\* code/qcommon/md4.c: -Werror.
	\\\\\\\* code/qcommon/common.c: -Werror.
	\\\\\\\* code/client/cl\\\\\\\_keys.c: -Werror.
	\\\\\\\* code/client/cl\\\\\\\_cin.c: -Werror, init local variables.	
	\\\\\\\* code/unix/Makefile: -Werror. need -O for -Wall for uninitialized
	Note: the above is the list of files that got touched during a pass
	with -g -O -Werror -Wall flags (in the hope of finding uninitialized
	memory and ambiguous statements). Most of the above are simply
	unused variables (or even code).

	TEST: RC3 data files, but DLL's.
	TODO: TA gets stuck in initial sound, doesn't play cinematics (sometimes)
	TODO: Q3 intro movie looses sound after Sarge gets teleported
	TODO: Q3 ingame renders world, weapon, muzzleflash, hud, can shoot,
	TODO:  but no movement, hud background is fubared. 

	\\\\\\\* code/cgame/cg\\\\\\\_main.c: cg\\\\\\\_singlePlayerActive

	\\\\\\\* code/q3\\\\\\\_ui/ui\\\\\\\_login.c: doesn't seem to be used?
	\\\\\\\* code/game/g\\\\\\\_rankings.c (G\\\\\\\_RankRunFrame): doesn't seem to be used.
	\\\\\\\* code/q3\\\\\\\_ui/ui.sh: disabled this. 
	\\\\\\\* code/q3\\\\\\\_ui/q3\\\\\\\_ui.sh: changed include path to ../q3\\\\\\\_ui/ (duh).

	\\\\\\\* code/game/game.sh: changed include path to ../q3\\\\\\\_ui/ which 
	is not in the Win32 batch file. 
	\\\\\\\* code/cgame/cg\\\\\\\_rankings.c: this does not seem to be included. 
	\\\\\\\* code/cgame/cgame\\\\\\\_ta.sh: added -DCGAME. Also added cg\\\\\\\_syscalls.c
	to build (also missing in Win32).

	\\\\\\\* code/cgame/cgame.sh: added -DCGAME (see cgame.bat). Also
	changed include path to ../q3\\\\\\\_ui/ which is not in the Win32
	batch file.  Also added cg\\\\\\\_syscalls.c to build (missing in 
	Win32).










### 2000-12-01  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* RC3: released as of sos001201 / Q3 1.27f

\\\* code/unix/Makefile: more fixes with clean build. The
changes made fix the menu rendering for Q3 but not TA.
Ingame graphics still broken.

\\\\\\\* code/game/game\\\\\\\_ta.sh: created. Use game\\\\\\\_ta.q3asm here.
	\\\\\\\* code/game/game.sh: no -DMISSIONPACK 
	\\\\\\\* code/game/game\\\\\\\_ta.q3asm: CR/LF, /.

	\\\\\\\* code/cgame/cgame\\\\\\\_ta.sh: created. Use cgame\\\\\\\_ta.q3asm here.
	\\\\\\\* code/cgame/cgame.sh:  no -DMISSIONPACK. No cg\\\\\\\_newdraw, ui\\\\\\\_shared.
	\\\\\\\* code/cgame/cgame.q3asm:  No cg\\\\\\\_newdraw, ui\\\\\\\_shared.
	CR/LF, /, cg\\\\\\\_newDraw, and the output path/name.
	
	\\\\\\\* code/q3\\\\\\\_ui/q3\\\\\\\_ui.q3asm: output to ui not q3\\\\\\\_ui...

	\\\\\\\* code/cgame/cg\\\\\\\_event.c: cg\\\\\\\_singlePlayerActive used here.
	TODO: guard by MISSIONPACK
	\\\\\\\* code/cgame/cg\\\\\\\_local.h: named q3print\\\\\\\_t enum. Cvar
	cg\\\\\\\_singlePlayerActive for both Q3 and TA.


	\\\\\\\* code/unix/Makefile: cleanly separate B/baseq3/ and
	B/missionpack/ subtrees during build. While new and old
	UI are in separate directories, the cgame/ and game/
	are shared, with conditional -DMISSIONPACK compile
	and different files includeds (cd\\\\\\\_draw, cg\\\\\\\_newdraw).
	That means twice the number of targets (3 DLL's, 3 QVM's,
	times two), and different build rules.
	TODO: carefully check Win32 build for (other) conditionals
	TODO: carefully check Win32 build for link lists

	\\\\\\\* CVS:  ui/, code/ui, botfiles/ and subdirectories are added.
	The code/macosx/ directory turned out to be a real pain that
	had to be edited manually, throwing out CVS/ directories in
	the tree that had been created by SOS as they are in id's
	repository:
	  code/macosx/Client/CVS
	  code/macosx/Client/PBUserInfo/CVS 
	  code/macosx/Client/Quake3.nib/CVS  
	  code/macosx/Common/CVS
	  code/macosx/DedicatedServer/CVS
	  code/macosx/DedicatedServer/PBUserInfo/CVS  
	Now tagged
	  cvs tag id1-26y-loki001119
	TODO: there are several new files not yet linked?

	\\\\\\\* ChangeLog: merged the Changelog from the bk00119 working
	branch (initial Q3TA port) based on sos001119 snapshot. Also
	merged the source tree with cvs-1.17.
	In the ChangeLog below  \\\\\\\*\\\\\\\*\\\\\\\* MISSIONPACK \\\\\\\*\\\\\\\*\\\\\\\* indicates work
	that was done on the branch (code-sos/ prefix in files).
	The cvs update of this will be tagged with
	 cvs tag id1-26y-loki001119
	Use this tag to hunt for possible Linux fixes that got lost
	(i.e. got dropped by id since id000516 and were thus not in
	sos001119, but did not show in diff id000516 cvs1-17).
	New directories in CVS: botfiles/, ui/.
	Missing from SOS/Missionpack: SDK directories.
	 common, lcc, libs, q3asm, q3data, q3map, q3radiant.


	\\\\\\\* ssreport.txt: below.
        Note: watch for files called "ssreport.txt", that's id ChangeLog.
	\\\\\\\* ui/ui\\\\\\\_syscalls.asm: below.
	\\\\\\\* q3\\\\\\\_ui/ui\\\\\\\_syscalls.asm: below.
	\\\\\\\* game/g\\\\\\\_syscalls.asm: below.
	\\\\\\\* cgame/cg\\\\\\\_syscalls.asm: below.
	\\\\\\\* bspc/linux-i386.mak: below.
	\\\\\\\* bspc/lcc.mak: below.
	\\\\\\\* botlib/linux-i386.mak: below.
	\\\\\\\* botlib/lcc.mak: below.
	\\\\\\\* A3D/a3d\\\\\\\_console\\\\\\\_variables.txt: CR/LF issue (minimize diffs).

	\\\\\\\* CVS: the checked bk001119 work copy of the sos001119 initial
	checkout (completed with everything in the SOS "Missionpack"
	tree, i.e. botfiles/ and botfiles.\\\\\\\* added), copied over the
	cvs-1.17 checkout.
	Note: in these cases, BEWARE ui -> q3\\\\\\\_ui/ links, and different
	ChangeLogs. Also "make clean" helps.

	\\\\\\\* unix/unix\\\\\\\_net.c: below. 
	\\\\\\\* unix/unix\\\\\\\_main.c: below. 
	\\\\\\\* unix/matha.s: below.
	\\\\\\\* unix/linux\\\\\\\_qgl.c: below.
	\\\\\\\* unix/linux\\\\\\\_glimp.c: see also linux\\\\\\\_joystick.c.
	\\\\\\\* server/sv\\\\\\\_client.c: below.
	\\\\\\\* renderer/tr\\\\\\\_surface.c: below.
	\\\\\\\* renderer/qgl.h: below.
	\\\\\\\* qcommon/qcommon.h: below.
	\\\\\\\* qcommon/files.c: below.
	\\\\\\\* qcommon/common.c: below.
	\\\\\\\* q3\\\\\\\_ui/ui\\\\\\\_demo2.c: below.
	\\\\\\\* mac/mac\\\\\\\_net.c: below.
	\\\\\\\* mac/mac\\\\\\\_glimp2.c: below.
	\\\\\\\* game/surfaceflags.h: below.
	\\\\\\\* game/bg\\\\\\\_lib.c: checked against id00516/cvs-1.17a diff.
	\\\\\\\* bspc/bspc.c: TH\\\\\\\_AASToTetrahedrons call removed since id000516.
	Note: our final compare of id000516 against cvs-1.17a, making sure
	that all these differences are in bk001119 (initial Q3TA port).
	If id branched the Q3TA base off before id000516 we might be screwed.
	Note: I do not diff against bk000520, which had some minor changes
	against id000516 (check VectorArrayNormalize, OTConfiguration), which
	seem consistent with me taking a pre-id000516 source snapshot for that
	working branch.










### 2000-11-30  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* TEST: compiled using the symbolic link ui/ -> q3\_ui/.
Had to undo one CVS change, regarding
code/cgame/cg\_syscalls.asm
code/game/g\_syscalls.asm
code/q3\_ui/ui\_syscalls.asm
These files are neither generated by Win32 cgame.bat
nor cgame.sh (etc.), thus seemingly maintained by hand.
cvs tag pr1-17-loki001130b
should be used if somebody needs this 1.17 snapshot
(which, remember, is post-release, with additional fixes).
Later:
cvs tag pr1-17-loki001130c
includes the full ChangeLog (duh).

\\\* CVS: up until cvs-1.17-001130, code/ui/ contained the
Q3 code for the UI QVM/DLL. In Q3TA, this code has been
moved to code/q3\\\_ui/, while at the same time the new
(scripting driven) UI code for Q3TA was maintained in
code/ui/. To preserve the history of code/ui/, it has been
renamed to q3/ui/ in the CVSROOT.
Note: this will BREAK all cvs-1.17 and before checkouts.
To compile earlier versions, move or link q3\\\_ui/ to ui/.
The code has been tagged
cvs tag pr1-17-loki001130
after the change.
DONE: remove code/\\\*/vm/\\\*.asm from CVSROOT
Note: this includes code/\\\*/\\\*.asm files (from \\\*\\\_syscalls.c).
These were originally tracked in CVS, but if we need
comparison of q3asm output or QVM files we can rely
on the Win32 and Linux SDK now. These files have been
physically removed from CVS now, followed by
cvs tag pr1-17-loki001130a





### 2000-11-30  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)      \*\*\* MISSIONPACK \*\*\*

\* RC2: new ZIP file (another 360M for convenience).

\\\* SOS: new CVS module, Quake3\\\_sos. This will be used to track
the unchanged SOS checkouts from id. As their repository
is read-only, and there is no estimate on when changes might
be backpropagated there, I will track their changes in a
separate module, and update our local Quake3 module
accordingly. This is effectively "tracking 3rd party"
w/o import and half-automated, forced mergers - in other
words, we now branch starting with our post-1.17 changes,
for the benefit of moving at all.
Baseline is a slightly changed PR-1.17 id000516 source dump
(essentially ui/ moved to q3\\\_ui for continuity, and CR/LF etc.).
cvs import Quake3\\\_sos id000516 pr1-17-win32
cvs import Quake3\\\_sos sos001119 pr1-26-win32
cvs import Quake3\\\_sos sos001120 pr1-26-win32-001120
cvs import Quake3\\\_sos sos001121 pr1-26-win32-001121
cvs import Quake3\\\_sos sos001122 pr1-26-win32-001122
cvs import Quake3\\\_sos sos001122-demo pr1-26-win32-demo
This is about the 1.26w Team Arena Win32 demo release, give or
take a couple of lines. Has Q3\\\_VERSION "Q3 Team Arena Demo 1.27b".
cvs import Quake3\\\_sos sos001123 pr1-26-win32-001123
cvs import Quake3\\\_sos sos001126 pr1-26-win32-001126
Now track id versions (see code/game/q\\\_shared.h:Q3\\\_VERSION)
cvs import Quake3\\\_sos sos001128 pr1-27c-win32-001128
With 1.27d they switched from Demo to full version (RC1).
cvs import Quake3\\\_sos sos001129 pr1-27d-win32-001129
cvs import Quake3\\\_sos sos001130a pr1-27d-win32-001130a
Now switched to 1.27e. This import is done from the SOS
working directory.
cvs import Quake3\\\_sos sos001130b pr1-27e-win32-001130b
Note: SoS created rwx attributes which are luckily fixed
automagically during import. It is also seemingly incapable
to compare files, and leave files that have not changed the
hell alone. I can't do cvs update due to the $..$ tags in
the original files (which CVS can't be told to ignore),
so I have to do import (creating a load of vendor tagged
branches), but at least cvsweb and cvs get the revisions
right.

\\\\\\\* code-sos/unix/Makefile: added linux\\\\\\\_joystick
	\\\\\\\* code-sos/unix/linux\\\\\\\_local.h: match mac/ and win32/, for prototypes.

	\\\\\\\* code-sos/unix/linux\\\\\\\_joystick.c: new file, code from linux\\\\\\\_glimp.c
	Note: decided to separate this, as (a) we might edit/extend
	a lot, (b), it's not in the id tree, (c) it's not GL, (d)
	there might be even more oddball devices. Anything that
	cuts down on diffs.

	\\\\\\\* code-sos/unix/linux\\\\\\\_glimp.c (Q\\\\\\\_stristr): const return (cvs1.17).
	Also (XLateKey): added more keyboard mappings (ASCII on
	upper row digits) (cvs1.17). Added in the minimal joystick
	hooks (cvars, function calls). Fixed joystick cvar naming
	to match win32 (kept joystick\\\\\\\_threshold). 
	TODO: joystick stubs for dedicated?

	\\\\\\\* CVS: I have to move up to 1.27d (data, Win32 networking).
	With exception of linux\\\\\\\_glimp.c (mostly joystick code), 
	all cvs1.17 changes should now be in the work snapshot 
	based on the first sos001119 we got from id. There are
	also some additional changes in there already, thus I'll
	move the (buggy) 1.26 snapshot into CVS before adding even
	more differences.





















### 2000-11-29  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)     \*\*\* MISSIONPACK \*\*\*

\* RC1: TeamArena\_Q3A\_RC1.zip. Source has moved from
Q3VERSION "Q3 Team Arena Demo 1.27c" to "Q3 1.27d" now.

\\\* code-sos/qcommon/common.c: added Com\\\_InitPushEvent(). Also
increased MAX\\\_PUSHED\\\_EVENTS to 256.
Note: this is another case of buffer memory not zero'ed.
Com\\\_EventLoop, fixed evTime to evType in debug print.

\\\\\\\* TEST: baseq3/
	 +set sv\\\\\\\_pure 0 +set vm\\\\\\\_game 0 +set in\\\\\\\_mouse 0 +set developer 2
        TODO: Team Arena in menu leads to RE\\\\\\\_Shutdown(1) and locks
	TODO: can't play game
	TODO: shaders can't load \\\\\\\*.tga, \\\\\\\*.jpg files are there
	TODO: DO\\\\\\\_CC linking for DLL's, DO\\\\\\\_SHLIB\\\\\\\_CC only for export?
	TODO: ERROR: Bad player movement angle
        TODO: Warning: cvar "..." given initial values: "..." and "..."
 	TODO: TA demo ERROR: CL\\\\\\\_ParseServerMessage: Illegible server message
        TODO: WARNING: Com\\\\\\\_PushEvent overflow

	\\\\\\\* code-sos/qcommon/files.c: add NULL filter for our Sys\\\\\\\_ListFiles calls.
	\\\\\\\* unix/unix\\\\\\\_shared.c (Sys\\\\\\\_ListFiles): signature has changed, 
	additional Sys\\\\\\\_ListFiles argument now.

	\\\\\\\* code-sos/unix/unix\\\\\\\_net.c (Sys\\\\\\\_GetPacket): see below (readcount=0).
	\\\\\\\* code-sos/unix/unix\\\\\\\_main.c: see below (Mike's and my changes to DLL
	loading, my event buffer clear fixes).
	\\\\\\\* code-sos/unix/linux\\\\\\\_qgl.c (QGL\\\\\\\_Init): see below (\\\\\\\_\\\\\\\_FX\\\\\\\_\\\\\\\_ guards).
	TODO: abstract WGL/GLX and end unfortunate QGL duplication.
	TODO: spice up QGL with Linux H2 full version.	
	\\\\\\\* code-sos/q3\\\\\\\_ui/ui\\\\\\\_demo2.c: fix on demo names  - no Q\\\\\\\_strupr(demoname).
	Note: in CVS this fix is in ui/ui\\\\\\\_demo2.c. CVS is screwed by
	id choosing the old name for new directory...
	TODO: manual intervention on "ui goes q3\\\\\\\_ui"  in CVSROOT?
	\\\\\\\* renderer/qgl.h: see below (\\\\\\\_\\\\\\\_FX\\\\\\\_\\\\\\\_ guards).
	\\\\\\\* qcommon/files.c: migrated in the 1.17cvs changes against the
	id000516 code dump, i.e. the (not marked - boo hiss) mkv changes.
	Note: all the above is based on a diff of the last id code dump
	pre-1.17 against our CVS, with those fixes now migrated into the
	sos1.26 snapshot.
	TODO: move in joystick code.
	TODO: replace XAutoRepeatOn/Off with filter (focus).
	TODO: DGA 2.0 and such.
	
	\\\\\\\* code-sos/game/q\\\\\\\_shared.c: valid compare for NULL strings
	\\\\\\\* code-sos/unix/unix\\\\\\\_main.c: QRTLD, and now using RTLD\\\\\\\_NOW.
	Note: it is a bad idea to load game DLL's that are missing symbols.

	\\\\\\\* code-sos/ui/ui\\\\\\\_main.c: see below.
	\\\\\\\* code-sos/game/g\\\\\\\_main.c: see below.
	\\\\\\\* code-sos/q3\\\\\\\_ui/ui\\\\\\\_main.c: see below.
	\\\\\\\* code-sos/cgame/cg\\\\\\\_main.c: made cvarTable and cvarTableSize static. This resolved
	a segfault related to traversing the UI table during Init.
	Note: there is a segfault related to this variable being out of bounds. 
	Different struct size in global variables possible aliasing between the 
	DLL's.
	
	\\\\\\\* code-sos/unix/unix\\\\\\\_main.c (Sys\\\\\\\_Error): assert(0), no exit in debug.
	\\\\\\\* code-sos/game/q\\\\\\\_shared.c: now aborts on NULL destination. Also DPrintf's
	on bogus excess copies.
	TODO: make all those string functions safe, at least assert.
	\\\\\\\* code-sos/server/sv\\\\\\\_init.c: comment in SV\\\\\\\_Init
	// init the botlib here because we need the pre-compiler in the UI
	Called in qcommon/common.c:Com\\\\\\\_Init, were CL\\\\\\\_Init is called afterwards...
	\\\\\\\* code-sos/server/sv\\\\\\\_bot.c: the botlib\\\\\\\_import is filled here.
	\\\\\\\* code-sos/unix/unix\\\\\\\_main.c (Sys\\\\\\\_GetBotLibAPI): RTLD\\\\\\\_NOW. Which is for naught,
	as this code is not used and has never been used. assert(0)

	\\\\\\\* code-sos/botlib/be\\\\\\\_interface.c: botimport supposed to be set here.
	\\\\\\\* code-sos/botlib/l\\\\\\\_memory.c: segfault with q3\\\\\\\_ui/ DLL.
        #1  0x80e23ec in GetMemory (size=35) at ..//botlib/l\\\\\\\_memory.c:331
        331             ptr = botimport.GetMemory(size + sizeof(unsigned long int));
	as botimport is completely NULL'ed.

	\\\\\\\* code-sos/q3\\\\\\\_ui/q3\\\\\\\_ui.sh: created from ui/ui.sh 1.17 

	\\\\\\\* code-sos/q3\\\\\\\_ui/q3\\\\\\\_ui.q3asm: unfubared (CR/LF, / path).

	\\\\\\\* code-sos/unix/Makefile: added q3\\\\\\\_ui/ make targets (basically
	ui/ targets from CVS 1.17 Makefile for starters).

	\\\\\\\* code-sos/q3\\\\\\\_ui/: this is the old UI code, which does not use
	../ui/menus.txt (see ui/ui\\\\\\\_main.c). In other words,
	the code in ui/ now has to be compiled or qvm'ed 
	for missionpack/, but to create the necessary DLL or
	QVM modules for baseq3/ we need to use q3\\\\\\\_ui/. 
	
	



















### 2000-11-27  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)     \*\*\* MISSIONPACK \*\*\*

\* code-sos/game/bg\_lib.c: ld problem with a custom "tan(..)"
TODO: loooking forward to SIGFPE on this code base.

\\\* code-sos/ui/ui\\\_util.c: this file is empty.

\\\\\\\* code-sos/ui/ui.sh: new files:
	  ui\\\\\\\_shared.c
	  ui\\\\\\\_util.c
	Replaced by the /ui/\\\\\\\*.menu files:
	 q3lcc: can't find `../ui\\\\\\\_cdkey.c'
	 q3lcc: can't find `../ui\\\\\\\_ingame.c'
	etc.

	\\\\\\\* code-sos/cgame/cgame.q3asm: added cg\\\\\\\_newdraw entry.
	Also added ui\\\\\\\_shared entry.
	\\\\\\\* cgame/cgame.sh: added cg\\\\\\\_newdraw.c entry.
	Also added ../ui/ui\\\\\\\_shared.c entry.

	\\\\\\\* code-sos/cgame/cg\\\\\\\_newdraw.c: renamed (was cg\\\\\\\_newDraw.c mixed case).
	Note: the infidels have taken over.

	\\\\\\\* cgame/cgame.sh: added  -DMISSIONPACK.
	Note: w/o, q3lcc complains
	../cg\\\\\\\_event.c:204: undeclared identifier `cg\\\\\\\_singlePlayerActive'
        ../cg\\\\\\\_event.c:204: left operand of . has incompatible type `int'
        which indicates that this source does not compile w/o MISSIONPACK
	anymore. The baseq3/pak4.pk3 file in the Q3TA snapshot archives
	are dated
	     284464  11-10-00 14:02   vm/cgame.qvm
             463940  11-14-00 14:47   vm/qagame.qvm
             271596  11-14-00 14:48   vm/ui.qvm
	the code dump is from 11-19. 
	Note: Make does not abort on q3lcc complains

	\\\\\\\* code-sos/game/game.sh: also added ai\\\\\\\_vcmd.c entry.

	\\\\\\\* code-sos/ui/ui.q3asm: fubared (below). In addition, this is 
	the only one to have a 
	 -o "/tmp/quake3/missionpack/vm/ui"
	line in it. Given that the other 2 QVM modules are
	also dependend on -DMISSIONPACK, this seems a real mess.
	For now using the same path as the other 3.
	\\\\\\\* code-sos/cgame/cgame.q3asm: below.
	\\\\\\\* code-sos/game/game.q3asm: fubared. Fixed CR/LF and \\\\\\\\ in paths
	again (read by q3asm called by game.sh called by make).
	\\\\\\\* unix/Makefile: updated fpor DLL/QVM.
	Note: also shell scripts to use q3lcc not lcc.

	



















### 2000-11-27  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* code/unix/Makefile: now expects a run/ directory
relative (between this, the Loki standards, and the
utility code in the same repository, it's ever so
slightly less dorky).
TODO: fix broken copyfiles target etc.pp.

\\\* code/game/bg\\\_lib.c: turns out the changes I
undid 001120 were affecting original Zoid
Linux port related defines, which break VM
compile. Mike fixed those (which I unfixed
when referring to the latest id code that does
not contain these patches). However, they
duplicate ANSI libc symbols, so the guards might
be wrong. The symbols are missing when compiling
for VM, so I now use the existing lcc -DQ3\\\_VM
flag:
//#if !defined ( \\\_MSC\\\_VER ) \\\&\\\& ! defined ( \\\_\\\_linux\\\_\\\_ )
#if defined ( Q3\\\_VM )
This will break DLL compile on non-ANSI platforms,
which will have to be added to the conditional then.

\\\\\\\* code/ui/ui.sh: below. 
	\\\\\\\* code/game/game.sh: below. 
	\\\\\\\* code/cgame/cgame.sh: Linux SDK installs q3lcc to
	avoid collisions with regular lcc pre-installs. The
	scripts fail with "lcc not found", but do not abort 
	the Makefile.
	Note: now that VM code gets actually built, there
	are errors:
	g\\\\\\\_main:648 ERROR: symbol vsprintf undefined
        bg\\\\\\\_pmove:1221 ERROR: symbol abs undefined
        q\\\\\\\_math:4309 ERROR: symbol fabs undefined
        q\\\\\\\_shared:2801 ERROR: symbol tolower undefined
        q\\\\\\\_shared:2862 ERROR: symbol toupper undefined
        ai\\\\\\\_dmq3:208 ERROR: symbol atoi undefined
        ai\\\\\\\_cmd:4951 ERROR: symbol sscanf undefined





















### 2000-11-20  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* TEST: test compile of pr-1.17+cvs fixes segfaults due
to new baseq3/pak4.pk3
Note: to self ... 1.17 is not compatible with new files.
Checking into CVS next.

\\\* code/: changes applied by us that are not in id's code base
affect q\\\_shared.c (NULL in Q\\\_stricmp), files.c (FIXME fs\\\_cdpath,
Sys\\\_ConcatenateFileList, ui\\\_demo2.c (demo no tolower on linux).
In unix/ linux\\\_glimp.c (joystick code), qgl.h, linux\\\_qgl.c (\\\_\\\_FX\\\_\\\_),
unix\\\_main.c (dlopen bug and event buffers), unix\\\_net.c (readcount),
matha.s (assembly warning).

\\\\\\\* code/server/sv\\\\\\\_client.c (SV\\\\\\\_WriteDownloadToClient): 
	No effective change  on FS\\\\\\\_SV\\\\\\\_FOpenFileRead call, they reworked 
	autodownload some more seemingly.

	\\\\\\\* code/renderer/tr\\\\\\\_surface.c: VectorArrayNormalize
	
	\\\\\\\* code/qcommon/qcommon.h: see below.
	\\\\\\\* code/qcommon/files.c: Com\\\\\\\_ReadConfigs removed.
	\\\\\\\* code/qcommon/common.c: removed Com\\\\\\\_ReadConfigs, 
	textual replacement of body in Com\\\\\\\_Init.

	\\\\\\\* code/mac/mac\\\\\\\_net.c: not applied (undone by id)
	OTConfiguration \\\\\\\*config \<> OTConfigurationRef  config

	\\\\\\\* code/mac/mac\\\\\\\_glimp2.c: r\\\\\\\_colorbits->integer > 16
	\\\\\\\* code/game/surfaceflags.h (CONTENTS\\\\\\\_BOTCLIP): added.

	\\\\\\\* code/game/q\\\\\\\_shared.h: not applied (undone by id)
	#if defined(ppc) || defined(\\\\\\\_\\\\\\\_ppc) || defined(\\\\\\\_\\\\\\\_ppc\\\\\\\_\\\\\\\_) 
        #define idppc 1 
	#else 
        #define idppc 0 
        #endif 

	\\\\\\\* code/game/q\\\\\\\_math.c: added another CPP line to guard
	BoxOnPlaneSide, removed WIN32 guard. 
	TODO: this could be broken code guarded in all current
	compiles...

	\\\\\\\* code/game/bg\\\\\\\_lib.c: left Q#\\\\\\\_VM guard for typedef cmp\\\\\\\_t
	Added !defined( \\\\\\\_\\\\\\\_linux\\\\\\\_\\\\\\\_ ) for tolower and atoi.
	Note: the changes above relate to the very last code update
	from id prior to the 6 month blackout, which were not in
	CVS when Michael made his updates. Needed to establish the
	baseline for the new patch. Source dump 1.17.00520, against
	SOS 1.26w-001119 version.
	









### 2000-11-20  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)       \*\*\* MISSIONPACK \*\*\*

\* TEST: running against the data up to TeamArena\_Q3A\_001109.zip
Hunk\_Clear: reset the hunk ok
Program received signal SIGBUS, Bus error.
"q3dm2", killBots==qtrue
#0  CM\_ClearMap () at ..//qcommon/cm\_load.c:644
#1  0x80884a7 in SV\_Map\_f () at ..//server/sv\_ccmds.c:159
#2  0x8072579 in Cmd\_ExecuteString (text=0xbffff4b0 "spmap q3dm2") at ..//qcommon/cmd.c:591
#3  0x8071dfe in Cbuf\_Execute () at ..//qcommon/cmd.c:190
#4  0x80763f7 in Com\_Frame () at ..//qcommon/common.c:2547
#5  0x8130d6b in main (argc=13, argv=0xbffff984) at ..//unix/unix\_main.c:953
#6  0x40100cb3 in \_\_libc\_start\_main (main=0x8130bc4 \<main\>
Not reproducible (screen stayed black).

\\\* TEST: +set developer 1, same for Win32 and Linux:
Can't find gfx/misc/flare.tga
Can't find gfx/misc/sun.tga
Can't find gfx/misc/console02.tga
Can't find vm/ui.map
Can't find textures/sfx/logo512.tga
Can't find gfx/colors/black.tga
Can't find models/mapobjects/banner/banner5\\\_2.md3
Can't find models/mapobjects/banner/banner5\\\_1.md3
Can't find textures/sfx/firegorre2.tga
Can't find textures/sfx/bolts.tga
Can't find menu/art/unknownmap.tga

\\\\\\\* Q3TA: after nearly 6 months, a code update from id. SOS access 
	even. Got it to compile, link and start, but it's currently broken
	(menu doesn't render in full, can't get into game etc.). Need
	a baseline 1.17 to diff against. Last code dump was May 16, with 
	bspc code updated May 19. Checking working directory of bk000520
	against CVS next (Mike's fixes never made it into id's codebase
	or a post 1.17 release, neither did my fixes as released in the
	point release version 1.17).










### 2000-11-19  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)       \*\*\* MISSIONPACK \*\*\*

\* TEST: Win32 install as tested with 1.26w. quake3.x86 (Q3A game)
Warning: cvar "r\_uifullscreen" given initial values: "1" and "0"
Warning: cvar "r\_inGameVideo" given initial values: "1" and "0"
^3WARNING: sound/feedback/hit.wav is a 8 bit wav file
(on windows, sound/weapons/weapon\_hover.wav is missing...)
Menu only partially displayed in TA and baseq3 play, menu itself
seems to work. Freetype?
WARNING: Com\_PushEvent overflow

\\\* code-sos/game/game.sh: not in SOS, moved in from CVS snapshot.

\\\\\\\* code-sos/qcommon/common.c: conditional DEDICATED to get rid off 
	CL\\\\\\\_ShutdownCGame/CL\\\\\\\_ShutdownUI/CIN\\\\\\\_CloseAllVideos.
	Same for UI\\\\\\\_usesUniqueCDKey: dedicated server does not
	write CD key file.
	TODO: check whether there is an unneeded "read CD key"
	for dedicated server.

	\\\\\\\* code-sos/null/null\\\\\\\_client.c (CL\\\\\\\_ShutdownAll): added dummy.

	\\\\\\\* code-sos/unix/Makefile:  server/sv\\\\\\\_net\\\\\\\_chan.o for dedicated server.

	\\\\\\\* code-sos/null/null\\\\\\\_snddma.c: fixed  S\\\\\\\_RegisterSound signature.

	\\\\\\\* code-sos/client/snd\\\\\\\_mix.c: snd\\\\\\\_p, snd\\\\\\\_linear\\\\\\\_count, snd\\\\\\\_out
	can't be static, as used by unix/snd\\\\\\\_mixa.s.

	\\\\\\\* code-sos/unix/Makefile: added to the executable target:
	   renderer/tr\\\\\\\_font.c
	   client/cl\\\\\\\_net\\\\\\\_chan.c
	   server/sv\\\\\\\_net\\\\\\\_chan.c 
	Also added a lot of jc\\\\\\\*.c files to build, to fix unresolved
	symbol errors.
	TODO: is there unused jpeg-6/jd\\\\\\\*.o code linked in now?

	\\\\\\\* code-sos/ft2/smooth.c: includes ftgrays.c, ftsmooth.c
	
	\\\\\\\* code-sos/ft2/truetype.c: ttdriver.c, ttpload.c, ttgload.c, ttobjs.c.
        Also (see ftoption.h) TT\\\\\\\_CONFIG\\\\\\\_OPTION\\\\\\\_BYTECODE\\\\\\\_INTERPRETER ttinterp.c
	
	\\\\\\\* code-sos/ft2/sfnt.c: includes ttload.c, ttcmap.c, sfobjs.c,
	sfdriver.c. lso (see ftoption.h)
        TT\\\\\\\_CONFIG\\\\\\\_OPTION\\\\\\\_EMBEDDED\\\\\\\_BITMAPS     ttsbit.c
        TT\\\\\\\_CONFIG\\\\\\\_OPTION\\\\\\\_POSTSCRIPT\\\\\\\_NAMES     ttpost.c

	\\\\\\\* code-sos/ft2/ftbase.c: includes ftcalc.c, ftobjs.c, ftstream.c,
	ftlist.c, ftoutln.c, ftextend.c, ftnames.c.
	
	\\\\\\\* code-sos/ft2/autohint.c: includes ahangles.c, ahglyph.c, ahglobal.c,
	ahhint.c, ahmodule.c.

	\\\\\\\* code-sos/unix/Makefile: added ft2/ to client objects, took out
	ftraster.c/ftrend1.c (see below), added -DFT\\\\\\\_FLAT\\\\\\\_COMPILE.
	\\\\\\\* ft2/ftsmooth.c: -DFT\\\\\\\_FLAT\\\\\\\_COMPILE required.
	\\\\\\\* ft2/raster1.c: -DFT\\\\\\\_FLAT\\\\\\\_COMPILE required.
	Note: this includes ftraster.c/ftrend1.c.

	\\\\\\\* code-sos/qcommon/vm\\\\\\\_x86.c: \\\\\\\_ftol is missing, ftolPtr only defined
	for Win32, but used in generic code. Workaround for now.
	TODO: find good Linux ftol, or use old solution. 

	\\\\\\\* SoS checkout. chown -R a+w \\\\\\\*  recode ibmpc:lat1 \\\\\\\*/\\\\\\\*.h \\\\\\\*/\\\\\\\*.c
	









### 2000-06-30  Michael Vance [briraeos@lokigames.com](mailto:briraeos@lokigames.com)

\* misc: Spoke with Leonardo about qvm mess.

\\\* ui/ui.sh: Created to build much like the ui.bat script.

\\\\\\\* ui/ui.q3asm: Use linux style paths.

	\\\\\\\* game/game.sh: Created to build much like the game.bat script.

	\\\\\\\* game/game.q3asm: Use linux style paths.

	\\\\\\\* cgame/cgame.sh: Created to build much like the cgame.bat script.

	\\\\\\\* cgame/cgame.q3asm: Use linux systel paths.

	\\\\\\\* unix/Makefile: Use the new .sh scripts to build the QVM files.

	\\\\\\\* lcc/etc/linux.c: Build .asm files instead of .s files.

	\\\\\\\* misc: QVMs now load properly, with minor glitches that should
	hopefully be solvable. The new build scripts conflict with the
	.asm files already in CVS, as the generated byte code is slightly
	different in some cases.
	









### 2000-06-29  Michael Vance [briareos@lokigames.com](mailto:briareos@lokigames.com)

\* lcc/makefile: Tweaked to automatically include the system
compiler's header location. Added an install directory.

\\\* lcc/custom.mk: Added a build directory.

\\\\\\\* lcc/etc/linux.c: Numerous small tweaks to make compiling the VM
	code a much simpler task.

	\\\\\\\* q3asm/Makefile: Created.

	\\\\\\\* q3asm/q3asm.c: Fixed uninitialized variable in
	HashString(). Fixed off by one in argument parsing.
	
	\\\\\\\* misc: Had Brian remove the Xmd.h include from glx.h so that we can
	build Quake3 on XFree86 4.0 systems.

	\\\\\\\* wine: Attempted to build with lcc.exe and q3asm.exe using wine,
	also did not work. This is in contrast to MikeP's .qvms, which
	seem to work.
	









### 2000-06-28  Michael Vance [briareos@lokigames.com](mailto:briareos@lokigames.com)

\* common/files.c: Fixed Mods menu behaviour.

\\\* unix/linux\\\_qgl.c: Guarded references to fxMesa.

\\\\\\\* renderer/qgl.h: Guarded references to fxMesa.

	\\\\\\\* ui/ui\\\\\\\_demo2.c: Don't convert filename to uppercase.
	









### 2000-05-07  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* common/cmdlib.c: windowism, not guarded. Added WIN32 around "ATOM a".

\\\* q3map/Makefile: Linux Makefile.

\\\\\\\* q3map/Makefile.irix: "makefile" in original code, Irix-only Makefile. 
	Just fixed some redundant TAB that GNU make despises about as much as I 
	despise GNU Make, and changed to a relative path.










### 2000-05-01  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* q3radiant/: updated with Q3Radiant198b3-src.zip.
Tagged (globally) as q3radiant-198b3.
Kept the old files
3DFXCamWnd.h
3DFXCamWnd.cpp
MainFrm2.cpp
New files
Shaders.h
misc/      (contributed special TGA resources, don't relly belong)
Removed:
pName
Changed filenames to previous case:
UNNAMED.MAP           -> unnamed.map
RES/BMP0002.BMP       -> RES/bmp00002.bmp
Changed:
changelog.txt         -> ChangeLog



### 2000-04-28  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* CVS: bk000425 modified sources. This replaces the unix/ directory
which is not yet in id's SourceSafe. Two check-ins, due to minor
changes in an attempt to nail the Voodoo3 related crashes (driver
problems, not a Q3 issue). Undid some of the QFL changes for PI
and the log bug fix - put back in (TODO). Also includes:
\* Quake3/code/botlib/be\_aas\_sample.c: single file update from Robert.

\\\* CVS: id000423 code dumps (two of them). Applying Loki patches.
Tagged for the final version (all patches).

\\\\\\\* CVS: id000422 code dump. This did not include the 1.16n fixes
	used for Linux, and was the first dump for the 1.17 security fix
	release.
	Note: forgot to check in the ft2/ headers themselves, but they
	are not used in the current codebase anyway. Are added in next
	dump. Also there is use of CVS/CVS-like $Keyword$ patterns in
	some files, and between their revisions and ours we fuck this up.
	Also, id ZIP files create write protected sources, have to do
	chmod -R a+w Quake3/ to work and overwrite files.

	\\\\\\\* CVS: bk000315 modified source. This version was the 1.16n release.
	Note: the changes applied here are not in the subsequent code dumps
	of id. If you want to compile the Linux version as released you
	have to use bk-tagged versions until the patches are merged in by
	Robert Duffy.

	\\\\\\\* CVS: id000314 engine code dump, same procedure as below, tag.
	Note: this version added vm/ sudirectories with assembly files
	for cgame, game, ui. CVS tag id000314.

	\\\\\\\* CVS: id000304 engine code dump. Now there is a problem, as CVS
	was used in the Mac sources. Do
	  find . -name 'CVS' -exec rm -r {} \\\\\\\\;
        before cvs update, then tagged:
	 cvs -d /loki/cvsroot/ tag id000304 Quake3/

	\\\\\\\* CVS: checked in a source snapshot of the id00303 engine code
	and the id0003029 tools code. The tool sources are not fully in 
	sync, and we have only partial source from earlier engine revisions.
        The engine source marks where Loki took over from Dave Kirsch.
        This snapshot (with all temporary and bogus files) is imported
        and tagged using:
          cvs -d /loki/cvsroot import Quake3 id000303 initial

        Modules:
          code:      the Q3 engine code, including a jpeg-6/ copy
          common:    code shared by tools
          libs:      code shared by tools, including a jpeg6/ copy
          q3asm:     VM bytecode assembly 
          q3data:    misc. Q3 data conversions
          q3map:     BSP builder
          q3radiant: Win32 editor, as is
          lcc:       C compiler for q3asm

        The sources have not been cleaned up, and binary files have not been
	removed. The Q3Radiant code base might exhibit mixed case asmbiguities
	in the future, and future source dumps might come from SourceForge
	instead.










### 2000-04-25  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* q3code.id000425/unix/Makefile: relative path, relocatable.
Note: first code merge with id, finally :-).



### 2000-04-24  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* q3code.bk000422/unix/matha.s: in C(BoxOnPlaneSide)
the following line triggers assembler warning:
"missing prefix `\*' in absolute indirect address, maybe misassembled!"
jmp Ljmptab(,%eax,4)



\\\* q3code.bk000422/unix/Makefile (MOUNT\\\_DIR): rember to change.
TODO: fix this bloody Makefile to be relocatable, damnit.

\\\\\\\* q3code.bk000422/cgame/cg\\\\\\\_event.c: applied JCash fix again
	(see EV\\\\\\\_EVENT\\\\\\\_BITS below). Send e-mail to verify.

	\\\\\\\* q3code.bk000422/renderer/tr\\\\\\\_image.c: "../jpeg-6/jpeglib.h" again.
	
	\\\\\\\* q3code.bk000422/: created from the id dump of today, lacking
	all but one of my changes (sigh). Swapped unix/ competely, takes
	care of 90%. Submitted all changes again to Robert...










### 2000-04-19  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* q3code.bk000315/unix/linux\_glimp.c (GLimp\_EndFrame):
QGL\_EnableLogging( r\_logFile->value ) doesn't work?

\\\* q3code.bk000315/unix/linux\\\_qgl.c:  GLimp\\\_LogNewFrame() is
obsolete. QGL\\\_EnableLogging was out of sync with Win32 and
did not support the new framecounter decrement logic.





### 2000-04-03  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* q3code.bk000315/server/sv\_snapshot.c: svs.nextSnapshotEntities
is a signed integer unconditionally incremented, which gets
negative and causes a segfaulting indexing an array. Added reset
to counter. Might fail if snapshot numbers are supposed to
monotonically increase.



### 2000-04-02  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* q3code.bk000315/client/cl\_parse.c (CL\_ParseServerMessage):
assert(0) on Illegible message (remember to +set in\_mouse 0).
TODO: have to add a dump message function, it's unreadable.

\\\* botlib/be\\\_ai\\\_goal.c (InitLevelItemHeap): loop counter -2
left -2 with uninitialized next, and -1 disconnected. Removed
redundant memset. There is an item alloc leak I suspect, as
max\\\_levelitems 1024 merely delayed the overflow error.





### 2000-04-01  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* botlib/be\_ai\_goal.c (InitLevelItemHeap): still segfaults.
Not memsetting the entire item heap. As items are cleared
on return, that leaves only memory corruption?
Later: upped max\_levelitems from 256 to 1024
Later: client dies on connect:
Error: CL\_ParseServerMessage: Illegible server message 255





### 2000-03-31  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* botlib/be\_ai\_goal.c: initializing global vars.
Segfault in AllocLevelItem ()
at /home/bk/Games/Quake3/q3code/botlib/be\_ai\_goal.c:364
I suspect that the initial freelevelitems setting is at
the end of the list and eventually exposed.

\\\* cgame/cg\\\_event.c: according to Johmn Cash:
itemNum = (es->event \\\& \\\~EV\\\_EVENT\\\_BITS) - EV\\\_USE\\\_ITEM0
Quote: "This causes itemNum to be invalid about half the time,
preventing any client side effect tied to the item from occurring."





### 2000-03-06  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* qcommon/common.c: set pushEvent buffer and indices
to zero in Com\_Init().

\\\* q3code/qcommon/qcommon.h: made SE\\\_NONE (and for paranoia
also NA\\\_BOT) explicitely set to zero.





### 2000-02-27  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* unix/Makefile: added dmalloc in an attempt to get on
the Z\_Free bug. Futile. Despite stripping dmalloc debug
token down to essentials, I get a (seemingly bogus or
unrelated):
debug-malloc library: dumping program, fatal error
Error: possibly bad .c filename pointer (err 24)





### 2000-02-26  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* qcommon/common.c: various debug builts to isolate the
Z\_Free bug. It reproducibly happens on some machines
with SE\_PACKET, but the packets themselves look
thoroughly corrupted.



### 2000-02-21  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* qcommon/common.c (Com\_EventLoop): possible problem
here, pointer does not get cleared.

\\\* unix/linux\\\_glimp.c (InitSig): no signal handler.
\\\* common/common.c: dump in Com\\\_Error for debug.





### 2000-02-17  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* q3code: new dump from Zoid. Repeat tr\_image.c fix.

\\\* unix/Makefile: added client/snd\\\_adpcm.c (linkage errors).
Later: added entire JPDIR and rules, for tr\\\_image.c.
Later: had to fix fules for game/ai\\\_\\\*.c files.
Later: removed ui/ui\\\_quit.o (n/a)
Later: took out -mpentiumpro -march=pentiumpro

\\\\\\\* renderer/tr\\\\\\\_image.c: windowism in #include path (see below).
         #include "..\\\\\\\\jpeg-6\\\\\\\\jpeglib.h"










### 1999-12-27  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* Alpha: tried a dedicated server compile. Segfaults in
../qcommon/files.c:1682, a paksort function doing pointer
fiddling.

\\\* Makefile.alpha: created.
Note: want to take the SDL/Setup autoconf ASAP.

\\\\\\\* unix/unix\\\\\\\_main.c: fixed \\\\\\\_\\\\\\\_axp\\\\\\\_\\\\\\\_ to \\\\\\\_\\\\\\\_alpha\\\\\\\_\\\\\\\_, guarded
	\\\\\\\_FPU\\\\\\\_SETCW.

	\\\\\\\* qcommon/vm\\\\\\\_alpha.c: dummy, created.
	\\\\\\\* qcommon/vm\\\\\\\_null.c: dummy, created.










### 1999-12-04  Bernd Kreimeier  [bk@lokigames.com](mailto:bk@lokigames.com)

\* renderer/tr\_image.c: windowism in #include path.
#include "..\\jpeg-6\\jpeglib.h"

\\\* Revision 1.11: from Zoid by e-mail.
Note: threw away my playground copy, starting with the
ZIP file. Zoid's using CVS now, but we can't remote
access it. Thus did the
"find . -name 'CVS' -exec rm -rf {} \\\\;"
and then track it as 3rd party source by



\\\\\\\* ChangeLog: created. Now starting to track Q3A source.










\--------- q3code log ---------------------------------------------

