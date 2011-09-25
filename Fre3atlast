@echo off
color 0c
echo have you temp rooted before using fre3vo?
:choice4
set /p C=(Y/N)? 
for %%? in (Y N) do if /I "%C%"=="%%?" goto ok4
goto choice
set C4=%C%4
goto %C4%
:ok4
:N4
echo clearing out cache by rebooting to prevent issues while exploiting
adb reboot
adb wait-for-device
PING 1.1.1.1 -n 1 -w 5000 >NUL
md5sum misc.img
type MD5.txt
echo is the misc.img MD5 sum as well as the original MD5. If they don't match please redownload.
adb shell getprop ro.bootloader
echo is your Hboot version
echo There are only 2 times this thing will stop.
echo - Right now to confirm you want to root and when you flash HBOOT.
echo This is just confirmation if you want to run it.  Enter Y or N.
:choice1
set /p C=(Y/N)? 
for %%? in (Y N) do if /I "%C%"=="%%?" goto ok1
goto choice1
:ok1
set C1=%C%1
goto %C1%
:Y1
cls
echo Starting
adb kill-server > NUL
adb push fre3vo /data/local/tmp
adb shell chmod 755 /data/local/tmp/fre3vo;/data/local/tmp/fre3vo -debug -start fbb58a00 -end FFFFFFFF
adb wait-for-device
adb push Superuser3-beta1.apk /data/app/
adb push su /data/local/tmp/
PING 1.1.1.1 -n 1 -w 5000 >NUL
adb wait-for-device 
adb shell cd /data/local/tmp;chmod 777 /data/local/tmp/su;cd /;mount -o remount,rw -t rootfs rootfs /;rm vendor;adb shell mkdir vendor;adb shell mkdir vendor/bin
adb wait-for-device
adb push su /vendor/bin/su
adb shell chmod 4755 /vendor/bin/su
cls
echo if you want to continue just hit Y and you can continue if not, hit N.
echo this is happening if you want to flash Hboot misc.img to be able to downgrade. -this is from saying N to the first choice
:N1
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
adb shell dd if=/sdcard/misc.img of=/dev/block/mmcblk0p17
adb pull /sdcard/misc.img miscpulled.img
cls
md5sum miscpulled.img
type MD5.txt
echo does it match?
:choice3
set /p C=(Y/N)? 
for %%? in (Y N) do if /I "%C%"=="%%?" goto ok3
goto choice3
:ok3
set C3=%C%3
goto %C3%
:Y3
echo * signature has been changed sucessfully!
Echo congrats on gaining root access.
echo Be sure to say thanks to OTAking and Scary for finding this out.
echo Glad to see that this file worked. Please leave feedback on the thread!
PING 1.1.1.1 -n 1 -w 5000 >NUL
echo if it doesnt say "su not found" then your rooted and this worked
adb shell su
PING 1.1.1.1 -n 1 -w 5000 >NUL
:N2
exit
:Y4
Fre3atlastreroot