How to use M8N GPS for F4V3S

M8N GPS and compass must be set up correctly to use, so be sure to read the following tutorial.

First should install the configurator ,make sure you install the latest version.

1.  betaflight-configurator: https://github.com/betaflight/betaflight-configurator/releases

2. cleanflight -configurator :https://github.com/cleanflight/cleanflight-configurator/releases

3. INAV-Configurator:https://github.com/iNavFlight/inav-configurator/releases

1.How to connect?

This is the interface definition diagram of F4V3S.




NOTE:GPS’s TX should connect to F4V3S’s RX, GPS’s RX should connect to F4V3S’s TX, This step is very important.

2.How to setup for M8N GPS?

set up for M8N GPS:


Then save and reboot.


Then save and reboot. Then you will see GPS mark is on.


2.How to setup for QMC5883 compass?

Note:if you use INAV firmware, no need this step, because INAV firmware can detect compass automatically. Betaflight and cleanflight firmware should do this step.


goto CLI screen to input command

resource I2C_SCL 2 B10
resource I2C_SDA 2 B11
resource SERIAL_TX 3 none
resource SERIAL_RX 3 none
set mag_bustype = I2C
set mag_i2c_device = 2
set mag_i2c_address = 0
set mag_hardware = AUTO
save

According to the above command input, press the ENTER key of the keyboard after each line of command input. Remember to enter the “save” command at the end, otherwise all commands will not work.

The above command means to disable serial 3 and enable I2C function, because serial port 3 and I2C share one interface, we must manually enable I2C and disable serial 3.

Then reboot the board.You will see the Mag mark is on.more information ,you can read here.https://www.rcgroups.com/forums/showthread.php?3073449-Omnibus-Nano-F4-v6/page15


