@echo off
color 0c
echo clearing out cache by rebooting to prevent issues while exploiting
adb reboot
adb wait-for-device
PING 1.1.1.1 -n 1 -w 5000 >NUL
md5sum misc.img
type MD5.txt
echo is the misc.img MD5 sum as well as the original MD5. If they don't match please redownload.
adb shell getprop ro.bootloader
echo this is your HBOOT VERSION
echo There are only 2 times this thing will stop. Right now to confirm you want to root and when you flash HBOOT.
echo This is just confirmation if you want to run it.
:choice1
set /p C=(Y/N)? 
for %%? in (Y N) do if /I "%C%"=="%%?" goto ok1
goto choice1
:ok1
set C1=%C%1
goto %C1%
:Y1
adb shell chmod 755 /data/local/tmp/fre3vo;/data/local/tmp/fre3vo -debug -start fbb58a00 -end FFFFFFFF
adb kill-server
adb start-server
adb shell cd /data/local/tmp;chmod 777 /data/local/tmp/su;cd /;mount -o remount,rw -t rootfs rootfs /;rm vendor;mkdir vendor;vendor/bin;cat /data/local/tmp/su > /vendor/bin/su;chmod 4755 /vendor/bin/su
echo This concludes obtaining root. Please make your choice about flashing the Hboot sig bypass.
adb shell su
echo if it tells you "not found" do a battery pull and then run the main script!
:choice2
set /p C=(Y/N)? 
for %%? in (Y N) do if /I "%C%"=="%%?" goto ok2
goto choice2
:ok2
set C2=%C%2
goto %C2%
:Y2
:N3
adb push misc.img /sdcard/misc.img
adb dd if=/sdcard/misc.img of=/dev/block/mmcblk0p17
adb pull /sdcard/misc.img miscpulled.img
cls
md5sum miscpulled.img
type MD5.txt
echo does it match?
:start
:choice3
set /p C=(Y/N)? 
for %%? in (Y N) do if /I "%C%"=="%%?" goto ok3
goto choice3
:ok3
set C3=%C%3
goto %C3%
:Y3
echo * signature has been changed sucessfully!
echo This concludes the re-rooting and the flashing of the hboot sig bypass. Enjoy!
:N1
:N2