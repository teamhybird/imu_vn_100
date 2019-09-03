# VN100 Usage on Hybird Technology drone

## Orbitty Carrier
We are using an Orbitty carrier board from ConnectTech to hold the Nvidia TX2 board.
[manual](http://connecttech.com/pdf/CTIM-ASG003_Manual.pdf)

This has a pinout of:

Pin 1: +3.3V OUTPUT (max 1A)
Pin 2: +5V OUTPUT (max 1A)
Pin 3: UART0 TX (3.3V) /dev/ttyS0  (vn100)
Pin 4: UART0 RX (3.3V) /dev/ttyS0  (vn100)
Pin 5: UART1 TX (3.3V) /dev/ttyTHS2  (MavLink)
Pin 6: UART1 RX (3.3V) /dev/ttyTHS2  (MavLink)
Pin 7/8/9/10: GPIO (3.3V)
Pin 11: I2C_CLK  (other imu)
Pin 12: I2C_DATA  (other imu)
Pin 13/14/15/17: Other
Pin 16/18/19/20: GND

4Mbps UART=linux limit
