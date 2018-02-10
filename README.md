# rpi3-setup
Raspberry Pi 3 - Extended Setup (Headless Support)

Setup Environment
WiFi: WPA2-PSK
Setup-Host: Windows 10 x64
SD Card: Samsung EVO Plus Micro SDHC 32GB

1) Download latest Raspbian Image
(Download: https://downloads.raspberrypi.org/raspbian_latest)

2) Optional: Format SD-Card with SD Card Formatter
(Download: https://www.sdcard.org/downloads/formatter_4/eula_windows/SD_CardFormatter0500SetupEN.exe)

3) Write Image to SD-Card with Win32 Disk Imager
(Download: https://netix.dl.sourceforge.net/project/win32diskimager/Archive/win32diskimager-1.0.0-install.exe)

4) Open "boot"-Partition with Windows Explorer

5) Create a blank file and name it "ssh" (without any extension)

6) Create a blank file, name it "wpa_supplicant.conf" and open it

7) Insert Content for "wpa_supplicant.conf" and save:
#DE for Germany - change it to the ISO/IEC alpha2 country code for the country in which your Pi is currently operating. 
country=DE
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="Name of your WiFi-SSID"
    scan_ssid=1
    psk="WiFi-Password"
    key_mgmt=WPA-PSK
}

8) Open the "config.txt"-file on the "boot"-Partition and add the following lines at the end
#I do not guarantee that these settings will work on your device. 
#In case of an error, the entries should be removed completely. 
arm_freq=1275
over_voltage=4
sdram_freq=575
sdram_schmoo=0x02000020
over_voltage_sdram_p=6
over_voltage_sdram_i=4
over_voltage_sdram_c=4
core_freq=500
v3d_freq=500
h264_freq=333
gpu_mem=256
dtparam=sdhost,overclock_50=80

9) 
