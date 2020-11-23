# Numlock-Script
A small script for seeing the status of NUMLOCK on keyboards that lack a light.
I found this script on a Reddit thread which has since been deleted (the author had also been a deleted account, but if you know who came up with this originally, let me know), because my ASUS TUF laptop does not have a light to indicate NUMLOCK's status.

This script, which you'll need AutoHotkey for, adds an icon in the taskbar to show you the status, which are controlled with the numbers. 44 is a golden star, indicating that numlock is on. 110 is a red circle with a cross, the universal NO sign, indicating that numlock is off. You can change these to whichever icons you desire.

Use Notepad++, or something similar, to create a file, copy the below script, name it whatever you want, and save it with a .ahk extension. You can then run it, and/or place it in your startup folder so that it'll run at boot.

~Numlock::  ; detect NumLock without blocking it (~)
    if (GetKeyState("NumLock", "T"))  ; get the toggle-state of NumLock
        #Persistent
		Menu, Tray, Icon, %A_WinDir%\System32\shell32.dll, 44 ; change icon (on)
    else
		#Persistent
		Menu, Tray, Icon, %A_WinDir%\System32\shell32.dll, 110 ; change icon (off)
    return
