
audio_ALC885
============
OS X Realtek ALC885 Onboard Audio

This guide enables OS X Realtek ALC885 onboard audio on Intel based motherboards with a bootable clean install of OS X. The Realtek AppleHDA.kext only works with the codec the kext was edited for and patches the native AppleHDA.kext.
____________________________________________________________Download ZIP >  > 

v2: 8/18/13 - 10.8.4 Shell Script Realtek ALC885 AppleHDA.kext Patching

Requirements
1. Native S/L/E/AppheHDA.kext (restore native AppleHDA.kext with Combo Update)
2. alc885-84 - Mountain Lion 10.8 - 10.8.4/AppleHDA.kext_v2.3.7

Realtek ALC AppleHDA Guides https://github.com/toleda/audio_ALCInjection
ML-Realtek ALC AppleHDA Capabilities.pdf
ML-Realtek ALC AppleHDA Screenshots.pdf
ML-Customizing the Realtek AppleHDA.pdf

One Realtek ALC885 AppleHDA.kext Audio_ID
Audio_ID: 1 supports 5 and 6 port ALC8xx onboard with/without AMD/Nvidia HDMI audio  

Audio_ID: 1 supports analog 5.1 surround sound
Audio_ID: 1 equires HDMI audio dsdt edits for HDMI audio 

Four techniques enable the Realtek ALC AppleHDA.kext, select one
http://www.insanelymac.com/forum/topic/290796-realtek-alc-applehda-audio-injection/
1. No dsdt/audio enabler = Audio_ID, install either kext (use 1a or 1b, not both)
1a. Audio_ID = 1/HDAEnabler1.kext https://github.com/toleda/audio_HDAEnabler1
1b. Audio_ID = 2/HDAEnabler2.kext https://github.com/toleda/audio_HDAEnabler2
2. dsdt/HDEF/layout-id = Audio_ID, see {Guide} Add or Edit dsdt/HDEF.pdf
2a. Audio_ID = 1/layout-id: 0x01, 0x00, 0x00, 0x00, 0x00
2b. Audio_ID = 2/layout-id: 0x02, 0x00, 0x00, 0x00, 0x00
2c. Audio_ID = 3, see dsdt/HD3K/HD4K HDMI audio
3. ssdt/HDEF/layout-id = Audio_ID, see {Guide} Add ssdt/HDEF.pdf
3a. Audio_ID = 1/layout-id: 0x01, 0x00, 0x00, 0x00, 0x00
3b. Audio_ID = 2/layout-id: 0x02, 0x00, 0x00, 0x00, 0x00
3c. Audio_ID = 3, see ssdt/HD3K/HD4K HDMI audio
4. Clover/Config.plist/PCI/HDAInjection, see ML-Clover Realtek ALC AppleHDA Injection.pdf
4a. Audio_ID = 1/HDAInjection=1
4b. Audio_ID = 2/HDAInjection=2
4c. Audio_ID = 3/HDAInjection=3 

Download
1. https://github.com/toleda/audio_ALC885
2. Select: Download ZIP (above and right)

Installation/Shell Script
1. Downloads/audio_ALC885-master/audio_alc885-84_patch.sh
2. Finder/File/Open With/Terminal
3. Enter password at prompt
4. Restart

Troubleshooting
1. ML-Realtek ALC AppleHDA Capabilities.pdf
2. Post to http://www.insanelymac.com/forum/topic/290797-mountain-lion-realtek-alc-applehda-audio/
3. Post to http://www.tonymacx86.com/audio/76309-mountain-lion-multibeast-no-audio-solutions-problem-reporting.html

Credit
THe KiNG 
VHC888
.:ErmaC:.
bcc9
RevoGirl

toleda
https://github.com/toleda/audio_ALC885
audio_alc885-84_patch.sh
README.txt
Files:
885.zip

Details - audio_ALC885-rv-patch script  (see Reqirements)

1. Verify: 
1a. native S/L/E/AppleHDA.kext
1b. Downloads/audio_ALC885-master

2. Rename or Delete (if present)
2a. Desktop/audio-ALC885 to Desktop/audio-ALC885-archive

3. Run script
3a. Downloads/audio_ALC885-master/audio_alc885-84_patch
3b. Finder/Open With/Other/Choose Application/Enable: All Applications
3c. Applications/Utilities/Terminal
3d. Enter Password when requested

4. Terminal/audio_alc885-84_patch window
_____________________________

Last login: Tue Aug 13 19:43:30 on console
$ . . ./Downloads/audio_ALC885-master/audio_alc885-84_patch.sh ; exit;
Prepare Desktop/audio_ALC885 ...
Archive:  885.zip
   creating: 885/
  inflating: 885/Info-84.plist       
 extracting: 885/layout1.xml.zlib       
  inflating: 885/Platforms.xml.zlib  
Install files ...
Password:
Patch binary/Optional - Default: No Patch
Fix permissions ...
Kernel cache...
Finished, restart required.
logout

[Process completed]
___________________________

5. If output is the same, success.  Restart

6. If errors or a different output;
6a. Install Desktop/audio_ALC885/AppleHDA-orig.kext to S/L/E/AppleHDA.kext
6b. Go to Step 1.
