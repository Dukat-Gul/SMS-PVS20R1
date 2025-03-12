# SMS-PVS20R1
Sunpower SMS-PVS20R1 Monitoring Infomation

Example setup of an SMS-PVS20R1 with 3 inverters communicating to it via the RS485.
Raspberry Pi 4 running NodeRed with ethernet connected the the SMS-PVS20R1 LAN2 port. Specifically not the LAN1 port as the SMS-PVS20R1 runs DHCP on that port. The LAN2 port is statically configured as 172.27.153.1 as a /24 (255.255.255.0).
Rpi4b's ethernet configured to have 172.27.153.254 
This nodered sketch is set to poll the SMS-PVS20R1's web interface every five minutes, strip out of the HTML response (note - its not JSON like the newer PVS5/6 units) and  take that information and upload it to pvoutput for each of the three inverters [and for giggles an aggregate virtual combined version].

Within this example substitute out SERIALNUMBER for each of the inverters which are identified in the SMS-PVS20R1's web interface also replace the API for the API key available in PVOutput.org and also the PVOUTPUT_SYSTEMID for the inverter being represented.
