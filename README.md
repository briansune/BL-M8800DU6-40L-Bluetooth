# BL-M8800DU6-40L BT Driver on Kernel 6.12.33

This is a bit different compared with Realtek or other BT devices.

In order to make this driver works there are ONE major setup is needed.

Under "aic_btusb.h" the default setting is required to change

```
// Default
#define CONFIG_BLUEDROID        1 /* bleuz 0, bluedroid 1 */
// On Ubuntu or other Linux
#define CONFIG_BLUEDROID        0 /* bleuz 0, bluedroid 1 */
```

Meanwhile on linux kernel .config user must not turn on any

```
Bluetooth device drivers  --->
 < > HCI USB driver
```

With all these setup, the compiled module .ko should able to run on 6.12.33-dirty

