////////////////////////////////////
	 Gpio.sh
 Assuming the path to GPIO exists on the target   
 /sys/class/gpio/gpio1/value
 Script reads and checks values of GPIO 1..10
////////////////////////////////////

var=1 & var=0 is used inly verify the script, on target replace the $var check
with commented cat /sys/class/gpio/gpio$i/value

test output
===========

./Gpio: 11: ./Gpio: cannot create /sys/class/gpio/gpio{1..10}/value: Directory nonexistent
All 10 pins are verified with input 0 and test result PASS
./Gpio: 46: ./Gpio: cannot create /sys/class/gpio/gpio{1..10}/value: Directory nonexistent
All 10 pins are verified with output 1 and test result PASS


////////////////////////////////////
	 EEPROM.sh
 Assuming the path to EEPROM exists on the target
 /sys/bus/i2c/devices/1-0050/eeprom
 Writes 8000 bytes of random data to EEPROM
 Reads them back and compares for a match
////////////////////////////////////

test output
===========

dd: failed to open '/sys/bus/i2c/devices/1-0050/eeprom': No such file or directory
dd: failed to open '/sys/bus/i2c/devices/1-0050/eeprom': No such file or directory
Files do not match result Fail
