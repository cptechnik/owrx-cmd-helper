# Notes to overclock # 

(press SHIFT on boot to disabling overclocking settings)

## overclock options ##
https://haydenjames.io/raspberry-pi-3-overclock/
https://www.raspberrypi.com/documentation/computers/config_txt.html#overclocking
### /boot/config.txt ###
arm_freq
over_voltage

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
governor-dialog-script: [2]

Commands:
lscpu
vcgencmd measure_clock arm
vcgencmd measure_volts core

Links:
* [1] https://raspberrypi.stackexchange.com/questions/9034/how-to-change-the-default-governor
* [2] https://github.com/DavidM42/rpi-cpu.gov
* https://www.elektronik-kompendium.de/sites/raspberry-pi/1911241.htm
