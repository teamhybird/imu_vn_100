# VN100 Usage on Hybird Technology drone

## Orbitty Carrier
We are using an Orbitty carrier board from ConnectTech to hold the Nvidia TX2 board.
[manual](http://connecttech.com/pdf/CTIM-ASG003_Manual.pdf)

This has a pinout of:


| P4 Orbitty      |                                         |
|-----------------|-----------------------------------------|
| Pin 1           | +3.3V OUTPUT (max 1A)                   |
| Pin 2           | +5V OUTPUT (max 1A)  (vn100)            |
| Pin 3           | UART0 TX (3.3V) /dev/ttyS0  (MavLink)   |
| Pin 4           | UART0 RX (3.3V) /dev/ttyS0  (MavLink)   |
| Pin 5           | UART1 TX (3.3V) /dev/ttyTHS2  (vn100)   |
| Pin 6           | UART1 RX (3.3V) /dev/ttyTHS2  (vn100)   |
| Pin 7/8/9/10    | GPIO (3.3V)  (unused)                   |
| Pin 11          | I2C_CLK  (could be other imu)           |
| Pin 12          | I2C_DATA  (could be other imu)          |
| Pin 13/14/15/17 | Other                                   |
| Pin 16/18/19/20 | GND   (MavLink and vn100)               |

4Mbps UART=linux limit

## Carrier board
On the Jetson TX2 large carrier board we wire the pins the same way, but to different jumpers.

|TX2     | J21    |            | Telem1 | Pixhawk Cube|
|--------|--------|------------|--------|-------------|
|uart0tx | Pin 8  | White wire | Pin 3  | serial1_tx  |
|gnd     | Pin 9  | Black wire | Pin 6  | gnd         |
|uart0rx | Pin 10 | Black wire | Pin 2  | serial1_tx  |

|TX2     | J21    |            | Rugged | IMU-VN-100  |
|--------|--------|------------|--------|-------------|
|+5V     | Pin 2  |            | Pin 1  | Power In    |

|TX2     | J17    |            | Rugged | IMU-VN-100  |
|--------|--------|------------|--------|-------------|
| Gnd    | Pin 1  |            | Pin 5  | Gnd         |
| rx     | Pin 4  |            | Pin 8  | tx          |
| tx     | Pin 5  |            | Pin 9  | rx          |
