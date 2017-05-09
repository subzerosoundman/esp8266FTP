# esp8266FTP
This repository contains arduino sketches related to FTP on the esp8266.

FTPESP8266.ino modifies SurferTim's FTP code (http://playground.arduino.cc/Code/FTP) to work with the esp8266 chip.This only contains the functionality to modify then upload a file to your server but additional functionality could easily be added by modifying the code starting at line 148. Functionality would be implemented usingraw FTP commands. A list of such commands can be found at: http://www.nsftools.com/tips/RawFTP.htm

The exp8266FTPThermometer.ino implements the code from the FTPESP8266.ino sketch to upload temperature data from a OneWire 1820 sensor. The data is uploaded every 10 minutes with data containing time from an NTP server, and both Celsius and Fahrenheit data from the sensor. Once a week, the data file will be renamed and uploaded. This allows for quicker uploads as each time the file is uploaded, the entire file has to be uploaded. This also allows for better backups as not every piece of data is logged in the same file so if something goes wrong on the ESP8266 you'll lose at most a week of data. This can be changed so you lose less. With minor modifications, this sketch can be used to upload nearly any kind of sensor data via ftp.
