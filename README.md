# miflora
shell script to read Xiaomi MiFlora sensor using gatttool and ash (busybox) only
(and gawk)
tested on OpenWRT 


note:
  gatttool/miflora times out regularly     
  script exits on failure but doesn't do retries.     

edited from https://www.fanjoe.be/?p=2741 
more info from https://wiki.hackerspace.pl/projects:xiaomi-flora 

# usage
(as root)
> ./miflora -M AA:BB:CC:00:11:22 -bvm

Battery: 92 %      
Version: 2.7.0      
Temperature 20.1 °C      
Light intensity: 76 lux     
Moisture: 14 %     
Fertility: 63 uS/cm     

# alternatively

> ./miflora -M AA:BB:CC:00:11:22 -H 48 -c | ./mifloracheck -msgcmd /bin/sendtotelegram

(will call /bin/sendtotelegram if values are out of range)
