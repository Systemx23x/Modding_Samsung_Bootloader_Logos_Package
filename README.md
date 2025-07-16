# Modding_Samsung_Bootloader_Logos_Package


## AllInOne - Updated 2025


Hi,<br>

This is a Tutorial to Modding the Bootloader Logos on your Samsung Devices, Please Add Supported or Not_Supported to the "Samsung_Devices_List_Overview.txt" so that Others can Check if or if Not can be Modded.<br>

Attention Devices befor 2019 use the File "param.bin", and Later than 2020 Devices use the File "up_param.bin" in the BL STOCK Firmware. Booth Files are After Modding Affect the Bootloader Logos of the Device.<br>

I have a Littlebit Collect for some Devices, in the Included Database are the Original STOCK Images, I have Add a little Tutorial Video how you Collect the Files for your Device, if you dont Found it Included.<br>

So we Need a Linux Distro or WSL or Binarys 4 Windows!!!!<br>

The Easiest is WSL in Windows 10/11 with a Installed Distro.<br>

## Basics
#########

## Compress/Decompress LZ4 Archives for Samsung
###############################################
````
Decompress Single LZ4 Archive
lz4 *.lz4
Example >>>
lz4 param.bin.lz4

Decompress Multi LZ4 Archives
lz4 -m *.lz4

Compress Single LZ4 Archive
lz4 -B6 --content-size "xxxx.xxx"
Example >>>
lz4 -B6 --content-size up_param.bin
lz4 -B6 --content-size param.bin

Compress Multi LZ4 Archives
lz4 -B6 --content-size -m "*.*"
Example >>>
lz4 -B6 --content-size -m *.bin


Compress/Decompress BIN Archive for Modding
###########################################

Decompress Single BIN Archive
7z x up_param.bin -oup_param
7z x param.bin -oparam

Compress Files to Single BIN File
7z a up_param.bin up_param/*.*
7z a param.bin param/*.*


Compress/Decompress LZ4 Archive to Tar Archive
##############################################

Compress File to TAR Archive
tar cvf modded_up_param.tar up_param.bin.lz4
tar cvf modded_param.tar param.bin.lz4

Decompress TAR Archive
tar xvf modded_up_param.tar
tar xvf modded_param.tar


Add a MD5sum to TAR Archive to verify in Odin3
##############################################

md5sum -t modded_up_param.tar >> modded_up_param.tar
md5sum -t modded_param.tar >> modded_param.tar


Rename TAR Archive to become a Odin3 Flashable Package
######################################################

mv modded_up_param.tar modded_up_param.tar.md5
mv modded_param.tar modded_param.tar.md5
````




## Thats Include in the Database
################################

````
Archive Software

Install WSL in Windows 10/11>>>>

dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

shutdown /r /t 0

PowerShell-7.5.2-win-x64.exe
wsl.2.5.9.0.x64.msi

pwsh\pwsh.exe -Command wsl --version
pwsh\pwsh.exe -Command wsl --install -d kali-linux

wsl.exe

sudo su
apt-get update -y && apt-get full-upgrade -y
apt-get install 7zip lz4 -y
apt-get autoclean -y && apt-get autoremove -y
clear
````

Archive Devices with Series and Models<br>
they Include param.bin.lz4/up_param.bin.lz4 STOCK Files,<br>
as Modding Base.<br>
````
Galaxy_A_Series >>>
A10_Series
A20_Series
A21_Series
A26_Series
A30_Series
A51_Series

Galaxy_M_Series >>>
M10_Series
M20_Series
M62_Series

Galaxy_S_Series >>>
S10_Series
S20_Series
S21_Series
S22_Series
S24_Series
S8_Series
S9_Series

Galaxy_Tab_Series >>>
Tab_A7_Lite_Series
Tab_A_10.1_Series
Tab_S6_Lite_Series
Tab_S_10.5_Series
Tab_S_8.4_Series

Galaxy_X_Series >>>
XCover_7_Series
XCover_Pro_Series
````

Archiv Examples Include SM-S901B Examoles of Modding and How it Works.<br>


Odin3-Packages<br>
up_param-Alien-Cleaned<br>
up_param-Gaming-Cleaned<br>
up_param-NetHunter-Cleaned<br>
up_param-Online-Cleaned<br>
up_param-XDA-Cleaned<br>

start_wsl.exe<br>

bash create_all.sh<br>

Script Look so >>>>>>><br>
````
!#/bin/sh
cd up_param-Alien-Cleaned
tar cvf up_param.bin *.jpg
lz4 -B6 --content-size up_param.bin
tar cvf up_param-Alien-Cleaned.tar up_param.bin.lz4
md5sum -t up_param-Alien-Cleaned.tar >> up_param-Alien-Cleaned.tar
mv up_param-Alien-Cleaned.tar up_param-Alien-Cleaned.tar.md5
7z a up_param-Alien-Cleaned.tar.md5.zip up_param-Alien-Cleaned.tar.md5
mv up_param-Alien-Cleaned.tar.md5.zip ../Odin3-Packages/
rm *.lz4
rm *.bin
cd ..
cd up_param-Gaming-Cleaned
tar cvf up_param.bin *.jpg
lz4 -B6 --content-size up_param.bin
tar cvf up_param-Gaming-Cleaned.tar up_param.bin.lz4
md5sum -t up_param-Gaming-Cleaned.tar >> up_param-Gaming-Cleaned.tar
mv up_param-Gaming-Cleaned.tar up_param-Gaming-Cleaned.tar.md5
7z a up_param-Gaming-Cleaned.tar.md5.zip up_param-Gaming-Cleaned.tar.md5
mv up_param-Gaming-Cleaned.tar.md5.zip ../Odin3-Packages/
rm *.lz4
rm *.bin
cd ..
cd up_param-NetHunter-Cleaned
tar cvf up_param.bin *.jpg
lz4 -B6 --content-size up_param.bin
tar cvf up_param-NetHunter-Cleaned.tar up_param.bin.lz4
md5sum -t up_param-NetHunter-Cleaned.tar >> up_param-NetHunter-Cleaned.tar
mv up_param-NetHunter-Cleaned.tar up_param-NetHunter-Cleaned.tar.md5
7z a up_param-NetHunter-Cleaned.tar.md5.zip up_param-NetHunter-Cleaned.tar.md5
mv up_param-NetHunter-Cleaned.tar.md5.zip ../Odin3-Packages/
rm *.lz4
rm *.bin
cd ..
cd up_param-Online-Cleaned
tar cvf up_param.bin *.jpg
lz4 -B6 --content-size up_param.bin
tar cvf up_param-Online-Cleaned.tar up_param.bin.lz4
md5sum -t up_param-Online-Cleaned.tar >> up_param-Online-Cleaned.tar
mv up_param-Online-Cleaned.tar up_param-Online-Cleaned.tar.md5
7z a up_param-Online-Cleaned.tar.md5.zip up_param-Online-Cleaned.tar.md5
mv up_param-Online-Cleaned.tar.md5.zip ../Odin3-Packages/
rm *.lz4
rm *.bin
cd ..
cd up_param-XDA-Cleaned
tar cvf up_param.bin *.jpg
lz4 -B6 --content-size up_param.bin
tar cvf up_param-XDA-Cleaned.tar up_param.bin.lz4
md5sum -t up_param-XDA-Cleaned.tar >> up_param-XDA-Cleaned.tar
mv up_param-XDA-Cleaned.tar up_param-XDA-Cleaned.tar.md5
7z a up_param-XDA-Cleaned.tar.md5.zip up_param-XDA-Cleaned.tar.md5
mv up_param-XDA-Cleaned.tar.md5.zip ../Odin3-Packages/
rm *.lz4
rm *.bin
cd ..
clear
````

And Include is a Not-/Supported Device List, they i have a little bit Refreshed >>>><br>


Please Feel Free to Add More Devices from here >>><br>
<a href=https://de.wikipedia.org/wiki/Samsung_Galaxy>Samsung WiKi </a><br>


How to Download Devices BL_xxxxxx.tar.md5 STOCK Firmware File, for Add param.bin/up_param.bin!!!!<br>

First goto Website<br>
<a href=https://www.samfw.com>https://samfw.com</a><br>

Than >>> Choose Device >>> Example >>><br>
<a href=https://samfw.com/firmware/SM-T510>https://samfw.com/firmware/SM-T510</a><br>

Choose CSC >>> Example >>><br>
<a href=https://samfw.com/firmware/SM-T510/DBT>https://samfw.com/firmware/SM-T510/DBT</a><br>

Choose latest Firmware >>> Example >>><br>
<a href=https://samfw.com/firmware/SM-T510/DBT/T510XXU5CWA1>https://samfw.com/firmware/SM-T510/DBT/T510XXU5CWA1</a><br>

Choose the Single File Download >>> Example >>><br>

Child files of T510XXU5CWA1 - If you want to download full firmware. Download one file ABOVE instead download all child files.<br>

AP_T510XXU5CWA1_CL22626479_QB61134385_REV02_user_low_ship_meta_OS11.tar.md5.zip<br>
BL_T510XXU5CWA1_CL22626479_QB61134385_REV02_user_low_ship.tar.md5.zip<br>
CSC_OMC_OXM_T510OXM5CVG2_CL22626479_QB54266617_REV02_user_low_ship.tar.md5.zip<br>
HOME_CSC_OMC_OXM_T510OXM5CVG2_CL22626479_QB54266617_REV02_user_low_ship.tar.md5.zip<br>


Choose Download >>> Example >>> BL_T510XXU5CWA1_CL22626479_QB61134385_REV02_user_low_ship.tar.md5.zip<br>
and Choose a Download Mirror.<br>

Open/Extract Archive BL_T510XXU5CWA1_CL22626479_QB61134385_REV02_user_low_ship.tar.md5.zip with 7zip >>> Open BL_T510XXU5CWA1_CL22626479_QB61134385_REV02_user_low_ship.tar.md5 with 7zip >>> 
Look if up_param.bin.lz4/param.bin/param.bin.lz4 in the Archive >>> when Yes Extract it, that mean that the Device is Supported, if you dont find one of the files, that mean Device is Not_Supported.<br>

Add It to Included Database in the Correct Device Archive.<br>


````
Samsung Galaxy A-Reihe
######################

Not_Supported    Samsung Galaxy A01
Not_Supported    Samsung Galaxy A01 Core
Not_Supported    Samsung Galaxy A2 Core
Not_Supported    Samsung Galaxy A02
Not_Supported    Samsung Galaxy A02s
Not_Supported    Samsung Galaxy A3 Core
Not_Supported    Samsung Galaxy A03
Not_Supported    Samsung Galaxy A03s
Not_Supported    Samsung Galaxy A03 Core
Not_Supported    Samsung Galaxy A04
Not_Supported    Samsung Galaxy A04s
Not_Supported    Samsung Galaxy A04 Core
Not_Supported    Samsung Galaxy A05s
Not_Supported    Samsung Galaxy A06
Supported    Samsung Galaxy A10
Supported    Samsung Galaxy A10e
Supported    Samsung Galaxy A10s
Supported    Samsung Galaxy A11
Supported    Samsung Galaxy A12
Supported    Samsung Galaxy A13
Supported    Samsung Galaxy A13 5G
Supported    Samsung Galaxy A14
Supported    Samsung Galaxy A14 5G
Supported    Samsung Galaxy A15
Supported    Samsung Galaxy A15 5G
Supported    Samsung Galaxy A16 5G
Supported    Samsung Galaxy A20 (2019)
Supported    Samsung Galaxy A20e (2019)
Supported    Samsung Galaxy A20s (2019)
Supported    Samsung Galaxy A21 (2020)
Supported    Samsung Galaxy A21s (2020)
Supported    Samsung Galaxy A22 (2021)
Supported    Samsung Galaxy A22 5G (2021)
Supported    Samsung Galaxy A23 (2022)
Supported    Samsung Galaxy A23 5G (2022)
Supported    Samsung Galaxy A25 5G (2024)
Supported    Samsung Galaxy A26 5G (2025)
Not_Supported    Samsung Galaxy A3
Not_Supported    Samsung Galaxy A3 (2016)
Not_Supported    Samsung Galaxy A3 (2017)
Supported    Samsung Galaxy A30 (2019)
Supported    Samsung Galaxy A30s (2019)
Supported    Samsung Galaxy A31 (2020)
Supported    Samsung Galaxy A32 (2021)
Supported    Samsung Galaxy A32 5G (2021)
Supported    Samsung Galaxy A33 (2022)
Supported    Samsung Galaxy A33 5G (2022)
Supported    Samsung Galaxy A34 5G (2023)
Supported    Samsung Galaxy A35 5G (2024)
Supported    Samsung Galaxy A36 5G (2025)
Supported    Samsung Galaxy A40 (2019)
Supported    Samsung Galaxy A41 (2020)
Supported    Samsung Galaxy A42 5G (2021)
Not_Supported    Samsung Galaxy A5
Not_Supported    Samsung Galaxy A5 (2016)
Not_Supported    Samsung Galaxy A5 (2017)
Not_Supported    Samsung Galaxy A50 (2019)
Not_Supported    Samsung Galaxy A50s (2019)
Supported    Samsung Galaxy A51 (2020)
Supported    Samsung Galaxy A51 5G (2020)
Supported    Samsung Galaxy A52 (2021)
Supported    Samsung Galaxy A52 5G (2021)
Supported    Samsung Galaxy A52s 5G (2021)
Supported    Samsung Galaxy A53 (2022)
Supported    Samsung Galaxy A53 5G (2022)
Supported    Samsung Galaxy A54 5G (2023)
Supported    Samsung Galaxy A55 5G (2024)
Supported    Samsung Galaxy A56 5G (2025)
Not_Supported    Samsung Galaxy A6
Not_Supported    Samsung Galaxy A60 (2019)
Not_Supported    Samsung Galaxy A7
Not_Supported    Samsung Galaxy A7 (2016)
Not_Supported    Samsung Galaxy A7 (2017)
Not_Supported    Samsung Galaxy A7 (2018)
Not_Supported    Samsung Galaxy A70 (2019)
Not_Supported    Samsung Galaxy A70s (2019)
Not_Supported    Samsung Galaxy A71 (2020)
Not_Supported    Samsung Galaxy A71 5G (2020)
Not_Supported    Samsung Galaxy A72 (2021)
Not_Supported    Samsung Galaxy A73 5G (2022)
Not_Supported    Samsung Galaxy A8
Not_Supported    Samsung Galaxy A8 (2016)
Not_Supported    Samsung Galaxy A8 (2018)
Not_Supported    Samsung Galaxy A8+ (2018)
Not_Supported    Samsung Galaxy A8s
Not_Supported    Samsung Galaxy A8s Unicorn Edition
Not_Supported    Samsung Galaxy A80 (2019)
Not_Supported    Samsung Galaxy A9 (2016)
Not_Supported    Samsung Galaxy A9 (2018)
Not_Supported    Samsung Galaxy A9 Star
Not_Supported    Samsung Galaxy A90 5G (2019)


Samsung Galaxy M-Reihe
######################

Not_Supported    Samsung Galaxy M01
Not_Supported    Samsung Galaxy M01s
Not_Supported    Samsung Galaxy M01 Core
Not_Supported    Samsung Galaxy M02
Not_Supported    Samsung Galaxy M02s
Supported    Samsung Galaxy M10
Supported    Samsung Galaxy M10s
Supported    Samsung Galaxy M11
Supported    Samsung Galaxy M12
Supported    Samsung Galaxy M13
Supported    Samsung Galaxy M15
Supported    Samsung Galaxy M20
Supported    Samsung Galaxy M21
Supported    Samsung Galaxy M21s
Supported    Samsung Galaxy M23 5G
Supported    Samsung Galaxy M30
Supported    Samsung Galaxy M30s
Supported    Samsung Galaxy M31
Supported    Samsung Galaxy M31s
Supported    Samsung Galaxy M32
Supported    Samsung Galaxy M33 5G
Supported    Samsung Galaxy M34 5G
Supported    Samsung Galaxy M40
Supported    Samsung Galaxy M42 5G
Supported    Samsung Galaxy M51
Supported    Samsung Galaxy M53 5G
Supported    Samsung Galaxy M55 5G
Supported    Samsung Galaxy M62


Samsung Galaxy S-Reihe
######################

Not_Supported    Samsung Galaxy R (GT-I9103)
Not_Supported    Samsung Galaxy S (GT-I9000)
Not_Supported    Samsung Galaxy S Advance (GT-I9070)
Not_Supported    Samsung Galaxy S Duos (GT-S7562)
Not_Supported    Samsung Galaxy S Duos 2 (GT-S7582)
Not_Supported    Samsung Galaxy S Plus (GT-I9001)
Not_Supported    Samsung Galaxy S Relay 4G (SGH-T699)
Not_Supported    Samsung Galaxy S Wi-Fi
Not_Supported    Samsung Galaxy SL (GT-I9003)
Not_Supported    Samsung Galaxy S II (GT-I9100)
Not_Supported    Samsung Galaxy S II Plus (GT-I9105)
Not_Supported    Samsung Galaxy S III (GT-I9300)
Not_Supported    Samsung Galaxy S III Neo (GT-I9301)
Not_Supported    Samsung Galaxy S III LTE (GT-I9305)
Not_Supported    Samsung Galaxy S III mini (GT-I8190)
Not_Supported    Samsung Galaxy S4 (GT-I9500, GT-I9505, GT-i9506 und GT-I9515)
Not_Supported    Samsung Galaxy S4 Active
Not_Supported    Samsung Galaxy S4 LTE+
Not_Supported    Samsung Galaxy S4 mini (GT-I9195)
Not_Supported    Samsung Galaxy S4 Zoom
Not_Supported    Samsung Galaxy S5 (SM-G900F)
Not_Supported    Samsung Galaxy S5 LTE-A/S5 LTE+, S5 LTE Plus (SM-G901F)
Not_Supported    Samsung Galaxy S5 Neo (August 2015)
Not_Supported    Samsung Galaxy S5 mini (SM-G800F)
Not_Supported    Samsung Galaxy S5 mini Duos (SM-G800H)
Not_Supported    Samsung Galaxy S6
Not_Supported    Samsung Galaxy S6 Edge
Not_Supported    Samsung Galaxy S6 Edge+
Not_Supported    Samsung Galaxy S7
Not_Supported    Samsung Galaxy S7 Edge (SM-G935F)
Not_Supported    Samsung Galaxy S7 Active
Supported    Samsung Galaxy S8
Supported    Samsung Galaxy S8+
Supported    Samsung Galaxy S9
Supported    Samsung Galaxy S9+
Supported    Samsung Galaxy S10
Supported    Samsung Galaxy S10+
Supported    Samsung Galaxy S10e
Supported    Samsung Galaxy S10 5G
Supported    Samsung Galaxy S10 Lite
Supported    Samsung Galaxy S20
Supported    Samsung Galaxy S20+
Supported    Samsung Galaxy S20 Ultra 5G (SM-G988N)
Supported    Samsung Galaxy S20 FE
Supported    Samsung Galaxy S20 FE 5G
Supported    Samsung Galaxy S21 (2021)
Supported    Samsung Galaxy S21+ (2021)
Supported    Samsung Galaxy S21 Ultra (2021)
Supported    Samsung Galaxy S21 FE (2021)
Supported    Samsung Galaxy S22 (2022)
Supported    Samsung Galaxy S22+ (2022)
Supported    Samsung Galaxy S22 Ultra (2022)
Not_Supported    Samsung Galaxy S23 (2023)
Not_Supported    Samsung Galaxy S23+ (2023)
Not_Supported    Samsung Galaxy S23 Ultra (2023)
Not_Supported    Samsung Galaxy S23 FE (2023)
Supported    Samsung Galaxy S24 (2024)
Supported    Samsung Galaxy S24+ (2024)
Not_Supported    Samsung Galaxy S24 Ultra (2024)
Not_Supported    Samsung Galaxy S24 FE (2024)
Not_Supported    Samsung Galaxy S25 (2025)
Not_Supported    Samsung Galaxy S25+ (2025)
Not_Supported    Samsung Galaxy S25 Ultra (2025)
Not_Supported    Samsung Galaxy S25 Edge (2025)


Samsung Galaxy XCover-Reihe
###########################

Not_Supported    Samsung Galaxy XCover 1 (GT-S5690)
Not_Supported    Samsung Galaxy XCover 2 (GT-S7710)
Not_Supported    Samsung Galaxy XCover 3 (SM-G388F)
Not_Supported    Samsung Galaxy XCover 4 (SM-G390F)
Not_Supported    Samsung Galaxy XCover 4s (SM-G398FN)
Not_Supported    Samsung Galaxy XCover 4s Enterprise Edition (SM-G398FZKDE28)
Supported    Samsung Galaxy XCover Pro (SM-G715FZKDE28)
Supported    Samsung Galaxy XCover 5 Enterprise Edition (SM-G525FZKDEEB)
Supported    Samsung Galaxy XCover 6 Pro (SM-G736BZKDEEB)
Supported    Samsung Galaxy XCover 7 (SM-G556B)[8]


Samsung Galaxy Z-Reihe (Foldables)
##################################

Not_Supported    Samsung Galaxy Fold
Not_Supported    Samsung Galaxy Z Fold2
Not_Supported    Samsung Galaxy Z Fold3
Not_Supported    Samsung Galaxy Z Fold4
Not_Supported    Samsung Galaxy Z Fold5
Not_Supported    Samsung Galaxy Z Fold6
Not_Supported    Samsung Galaxy Z Flip
Not_Supported    Samsung Galaxy Z Flip 5G
Not_Supported    Samsung Galaxy Z Flip3
Not_Supported    Samsung Galaxy Z Flip4
Not_Supported    Samsung Galaxy Z Flip5
Not_Supported    Samsung Galaxy Z Flip6


Samsung Galaxy Tablet-Reihe
###########################

Supported    Samsung Galaxy Tab S 8.4
Supported    Samsung Galaxy Tab S 10.5 All-Models
Not_Supported    Samsung Galaxy Tab S2 All-Models
Not_Supported    Samsung Galaxy Tab S3 All-Models
Not_Supported    Samsung Galaxy Tab S4 All-Models
Not_Supported    Samsung Galaxy Tab S5 All-Models
Supported    Samsung Galaxy Tab S6 Lite
Not_Supported    Samsung Galaxy Tab S7 All-Models
Not_Supported    Samsung Galaxy Tab S8 All-Models
Not_Supported    Samsung Galaxy Tab S9 All-Models
Not_Supported    Samsung Galaxy Tab A Series 2015-2018
Supported    Samsung Galaxy Tab A 10.1 2019
Not_Supported    Samsung Galaxy Tab A8 Series
Supported    Samsung Galaxy Tab A7 Lite Series
Not_Supported    Samsung Galaxy Tab A 8.0 Series
````

The Package Size is ca.550MB as ZIP Archive <<<<br>
Download Here >>> <a href=https://c.1und1.de/@1157988897574099954/5-j-65tuJOvNnUEt7XbbIA>Full Package AllInOne 2025 - Size ~550MB</a><br>

Example Logos i Add in this Thread, and Yes Thats All 4 Now.<br>

HaveFun.<br>

## Example ScreenShots >>>

## Cleaned Base in Every Modding>>>
````
![warning_svb](https://github.com/user-attachments/assets/ba2cc9f8-46cc-44f3-a830-2b37bc2b8c0f)
![warning](https://github.com/user-attachments/assets/2e31e152-2ae4-457d-9fbd-2219c0a7ce16)
![secure_error](https://github.com/user-attachments/assets/b84f6c34-d092-49b7-ab52-0df9e20d7c88)
![download_error](https://github.com/user-attachments/assets/775c22d4-0fbf-4b52-afa7-335664ea52e4)
![download](https://github.com/user-attachments/assets/120034e0-efee-4270-be85-a605296e7f5a)
![device_unlock](https://github.com/user-attachments/assets/773ce1e3-739a-422d-9748-7edc45c21b42)
![device_lock](https://github.com/user-attachments/assets/d34afb61-ee6a-430e-8532-1f6772106857)
````

## up_param-Alien-Cleaned >>>
````
![svb_orange](https://github.com/user-attachments/assets/359795fa-9eb9-4f01-9918-9b84ce97f6f1)
![booting_warning](https://github.com/user-attachments/assets/a66f424f-096c-422f-a75a-24160dc8b7e0)
![android_logo](https://github.com/user-attachments/assets/dfc06a2f-bb20-4df2-a944-1c00b86c0bda)
````
## up_param-Gaming-Cleaned >>>
````
![svb_orange](https://github.com/user-attachments/assets/8fe84966-7246-493f-8585-e9f681677d5f)
![booting_warning](https://github.com/user-attachments/assets/a978e556-72c6-4af1-99f6-7be5f878dc10)
![android_logo](https://github.com/user-attachments/assets/4e09f254-b1fe-41cf-99ff-73fc74da540c)
````
## up_param-NetHunter-Cleaned >>>
````
![svb_orange](https://github.com/user-attachments/assets/620c53d4-33a2-4f42-8ff1-f20c7c39198f)
![booting_warning](https://github.com/user-attachments/assets/544d560a-f81a-4444-a2a8-96a6f82bd078)
![android_logo](https://github.com/user-attachments/assets/1cfe3997-e5c7-45f5-ada2-700c3636fd9f)
````
## up_param-Online-Cleaned >>>
````
![svb_orange](https://github.com/user-attachments/assets/e52b4e5c-72aa-4e7c-83de-7ab38207091c)
![booting_warning](https://github.com/user-attachments/assets/6940a2c5-130d-4374-b7d6-4c853f189910)
![android_logo](https://github.com/user-attachments/assets/a707a221-92d3-4cf9-a23f-3b211bdee273)
````
## up_param-XDA-Cleaned >>>
````
![svb_orange](https://github.com/user-attachments/assets/ea031899-0776-4c9a-ae31-667afc62cab5)
![booting_warning](https://github.com/user-attachments/assets/a02975e5-14cd-4cff-aa2f-506b4281a617)
![android_logo](https://github.com/user-attachments/assets/96068a16-4aa6-4cc9-87ad-9cae1fabadb3)
````
