# How-to-DD
Using DD in Windows for cloning disk, etc. ...

### What you need
- Git For Windows (portable version)
- https://gist.github.com/r-a-y/da6c3b1b99aafcb3e97e311280aa9434

It contains Unix like commands for Windows like dd, etc.

~~~cmd
# show all your disks in Windows:
wmic diskdrive list brief

# output looks similar like this ...
Caption                                DeviceID            Model                                  Partitions  Size
WDC WD10JPVX-75JC3T0                   \\.\PHYSICALDRIVE0  WDC WD10JPVX-75JC3T0                   1           1000202273280
Micron_1100_MTFDDAV256TBN              \\.\PHYSICALDRIVE2  Micron_1100_MTFDDAV256TBN              3           256052966400
LITEONIT L8T-256L9G-11 M.2 2280 256GB  \\.\PHYSICALDRIVE1  LITEONIT L8T-256L9G-11 M.2 2280 256GB  3           256052966400
Microsoft Virtual Disk                 \\.\PHYSICALDRIVE3  Microsoft Virtual Disk                 0           274872407040
~~~
- For more info on WMIC
- https://ss64.com/nt/wmic.html

Another way to find disk devices is to have a look in the /dev folder on Windows with ls-command
~~~bash
ls -C /dev

# gives an output like this ...
E:\PortableGit\usr\bin>ls -C /dev
clipboard  full    ptmx    sda1  sdb3  sdc2  sdd1    stdout   zero
disk       mixer   pty0    sdb   sdb4  sdc3  shm     tty
dsp        mqueue  random  sdb1  sdc   sdc4  stderr  urandom
fd         null    sda     sdb2  sdc1  sdd   stdin   windows

# shows all the drives from sda to sdd with partitions sda1 to sdd1
# compared to the wmic-command before
~~~

This is usefull in dd-commands
~~~
# like
dd if=\\.\PHYSICALDRIVE0 of=\path\to\WDC WD10JPVX-75JC3T0.dd status=progress
# or
dd if=/dev/sda of=\path\to\WDC WD10JPVX-75JC3T0.dd status=progress
~~~
