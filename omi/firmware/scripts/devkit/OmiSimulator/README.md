# Omi Simulator

Simulator of BasedHardware Omi device.

This is an early version, code needs cleaning, proper error handling, ...

## Limitations

On the Mac, name advertised for the BLE Peripheral is the name of the machine.

The latest source code of the Omi app discovers and connects to the Omi device by service UUID, so this works fine.

However, previoys versions of the Omi app looked for a device named "Friend" (or "Super").

One solution is to rename your machine to one of those names.  

If you need to work with older code, another solution is to rebuild the Omi app yourself.  
In AppWithWearable project, in file /lib/utils/ble/scan.dart, at line 11, add the name of your machine to the condition, like  
``` dart
(device) => device.name == 'Friend' || device.name == 'Super' || device.name == 'my machine name',
```
