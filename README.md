# CisTracer
# You provide a mac, ip, or list of mac/ips as input and the ip and port of correct switch and host-connected switchport is returned/written.


Files: 
findMac.py - main program, run this python module to use the program. Loads all dependencies and kicks off the trace. 
ciscoApi.py - A custom class to be used as a rudimentary API for intefacing with Cisco IOS, NXOS, IOS-XR devices. 
config.ymL - Config file, required options to be set documented in config comments and below. 
result.txt - This is where the results of the trace are written. 
logs.txt - This is the log file where the program writes its debug and info logs. 
mac_input.csv - This is an input file, use it with the config file option to automAtically parse a list of mAcs and trace them. You just need a .csv file with the first row                   col A as “Mac Addresses”, followed by each mac in each Col A row below it. 
Logger.psy - This is the logger class created for custom logging. 

Config options: 
Connection_params - loaded as dictionary used for connecting to cisco ios appliances via netmiko; modify first_switch value to the
  ip of switch/ L2/L3 appliance you would like to begin tracing from (usually a core or distribution layer switch). 

Notes: 
- Gracefully handles instances where device that shows up as a CDP neighbor is not a switch (this can happen in the case of VoIP phones
  with pc’s daisy chained, as well as WAPs). Returns the interface & switch that the VoIP phone or WAP is connected to. 

Improvements: 
- Plan to add options/support to trace switch/port based on IP address, as well as MAC address. 
- Due to time constraints and deadlines that had to be met using this tool, the program became spaghetti code as I implemented quick fixes and duct taped solutions to
  random unforseen situations and problems that arose. These functions and overall architecture of this program can greatly be improved upon
  optimized/re-coded in a more efficient or human readable/understandable way
