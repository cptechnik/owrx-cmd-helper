# Notes to overclock # 
(press SHIFT on boot to disabling overclocking settings)

## overclock options ##
https://haydenjames.io/raspberry-pi-3-overclock/
https://www.raspberrypi.com/documentation/computers/config_txt.html#overclocking
### /boot/config.txt ###
arm_freq
core_freq
over_voltage
gpu_freq

## overclocking freq tips ##
https://magpi.raspberrypi.com/articles/how-to-overclock-raspberry-pi-4
https://raspberry.tips/raspberrypi-tutorials/raspberry-pi-3-uebertakten


## governor [1] ##
* standard: ondemand
* R: cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_governor
* W:
  * sudo sh -c "echo powersave > cpu0/cpufreq/scaling_governor"
  * sudo sh -c "echo performance > cpu0/cpufreq/scaling_governor"
  * posssible: conservative, ondemand, userspace, powersave, performance, schedutil
### governor-dialog-script: [2]
### cpufrequtils
sudo apt install cpufrequtils
sudo cpufreq-set -g powersave
sudo cpufreq-set -u 1400MHz -d 600MHz         # (example for pi3b+; max is set in boot.txt) 

## cpu freq
in MHz
(https://www.elektronik-kompendium.de/sites/raspberry-pi/1912241.htm)
(https://raspberry.tips/raspberrypi-tutorials/raspberry-pi-3-uebertakten)
(https://magpi.raspberrypi.com/articles/how-to-overclock-raspberry-pi-4)
* Pi model A, A+, B andand B+Pi modelmodel A, A+, B and B+
  * base/standard 700
  * possible 1000
* Pi model A, A+, B andand B+Pi modelmodel A, A+, B and B+
  * poss 1100 with core_freq and sdram_freq=450
* Pi 2
  * base 600
  * standard 900 / 1000 with core_freq=500 and over_voltage=2
  * possible 1200
* Pi 3
  * standard 1200
  * possible 1350
    * with core_freq=500 and sdram_freq=500 and over_voltage=4
    * (upto 1400 some bootfail)
* Pi 3+
  * standard 1400
  * possible 1500 at over_voltage=4
* Pi 4
  * standard 1500 / 2200
  * possible 2000 (upto 2147 some bootfail) at over_voltage=6
  * no sdram overclocking supported
  * gpu std 500, possible 750 
* Raspberry Pi Zero / Zero W
  * possible possible1100 with core_freq=450 and over_voltage=6 



Commands:
lscpu
vcgencmd measure_clock arm
vcgencmd measure_volts core

Links:
* [1] https://raspberrypi.stackexchange.com/questions/9034/how-to-change-the-default-governor
* [2] https://github.com/DavidM42/rpi-cpu.gov
* https://www.elektronik-kompendium.de/sites/raspberry-pi/1911241.htm
* https://www.tomshardware.com/how-to/overclock-any-raspberry-pi
