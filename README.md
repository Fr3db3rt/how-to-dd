# How-to-DD
Using DD in Windows for cloning disk, etc. ...

### What you need
- Git For Windows (portable version)
  https://gist.github.com/r-a-y/da6c3b1b99aafcb3e97e311280aa9434

It contains Unix like commands for Windows like dd, etc.

~~~
# show all your disks in Windows:
wmic diskdrive list brief

# output looks similar like this ...
Caption                                DeviceID            Model                                  Partitions  Size
WDC WD10JPVX-75JC3T0                   \\.\PHYSICALDRIVE0  WDC WD10JPVX-75JC3T0                   1           1000202273280
Micron_1100_MTFDDAV256TBN              \\.\PHYSICALDRIVE2  Micron_1100_MTFDDAV256TBN              3           256052966400
LITEONIT L8T-256L9G-11 M.2 2280 256GB  \\.\PHYSICALDRIVE1  LITEONIT L8T-256L9G-11 M.2 2280 256GB  3           256052966400
Microsoft Virtual Disk                 \\.\PHYSICALDRIVE3  Microsoft Virtual Disk                 0           274872407040
~~~
- For more info on WMIC, https://ss64.com/nt/wmic.html



  
