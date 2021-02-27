# How to install macOS Big Sur on an Unsupported Mac
## My Test: MacBook Pro Late 2011


1. By "Disk Utility" => add "New Volume" to "Your SSD" as "APFS format"

2. By "Disk Utility" => format USB : from top device (Erase : Mac OS Extended (Journaled)) : 
     after select "Show All Devices" : then "Erase" from Top of "USB"
	* Name  :  MyVolume  
	* Format :  Mac OS Extended (Journaled)
        * Schme  : GUID Partition Map
    - if you use "SD Card", do not use "USB hub", use "usb sd card reader"

3. Download : InstallAssistant.pkg
http://swcdn.apple.com/content/downloads/50/49/001-79699-A_93OMDU5KFG/dkjnjkq9eax1n2wpf8rik5agns2z43ikqu/InstallAssistant.pkg
https://forums.macrumors.com/threads/macos-11-big-sur-on-unsupported-macs-thread.2242172/

4. Run "InstallAssistant.pkg" for install app "Install macOS Big Sur"
    -- or from "App Store" search for "macOS big sure" -> get

5. From "Terminal" run command : after go to : Application -> "Install macOS Big Sur" -> "Show Package Contents" :
	sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

6. Download code from "https://github.com/barrykn/big-sur-micropatcher"

7. From "Terminal" run command "micropatcher.sh" to "USB" ("Install macOS Big Sur") :
   .../micropatcher.sh /Volumes/Install\ macOS\ Big\ Sur 

8.  From "Terminal" run command "install-setvars.sh" to "USB" ("Install macOS Big Sur") :
   .../install-setvars.sh /Volumes/Install\ macOS\ Big\ Sur

9.  Restart your Mac and press "alt" key until see the "apple" logo, then select your USB ("Install macOS Big Sur") 
     - after go to "Recovery" go to "Terminal" from "Utility menu" then :
	* run command "csrutil disable"  ***************
	* run command "csrutil authenticated-root disable"
    - select "Install macOS" for "Install macOS Big Sur" and select "Your SSD"

10. After install "macOS Big Sure" :
	* Plug in USB "Install macOS Big Sur"  then restart Your Mac and press "ALT" key then select your "macOS Big sure" disk
  	* From "Terminal" run command : for fix wifi
   	    /Volumes/Install\ macOS\ Big\ Sur/patch-kexts.sh --2011
  	* Restart Your Mac and press "ALT" key then select your "macOS Big sure" disk
  
11. Modifying the System volume yourself :
  	* From "Terminal" run command : 
          /Volumes/Install\ macOS\ Big\ Sur/remount-sysvol.sh

# Sources :
[Source 1](https://www.youtube.com/watch?v=nyGRN6gXYUw)
[Source 2](https://github.com/barrykn/big-sur-micropatcher)
[Source 3](https://www.macworld.co.uk/how-to/update-mac-os-3521995/)
[Source 4](https://www.youtube.com/watch?v=qzf7eAzMlPg)
