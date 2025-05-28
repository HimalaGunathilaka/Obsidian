|                             |                                                                                      |
| --------------------------- | ------------------------------------------------------------------------------------ |
| Typical measuring range     | 0.15~8m                                                                              |
| Sampling frequency          | 2300 Hz                                                                              |
| Scan frequency              | 6 Hz                                                                                 |
| Angular resolution          | ≤1°                                                                                  |
| Mechanical size             | 96.3*59.8*38.8mm                                                                     |
| Communication interface     | UART @ 115200bps                                                                     |
| Power supply                | 5V                                                                                   |
| Working current             | 240mA                                                                                |
| Power consumption           | ≈1.3W                                                                                |
| Operating temperature range | -10℃~40℃                                                                             |
| Scanning range              | 360°                                                                                 |
| Ranging accuracy            | 5mm (< 1 m)  <br>1.5% of actual distance (1~6 m)  <br>2% of actual distance (6~ 8 m) |
![[Pasted image 20250527180955.png]]

| No  | Function | Type   | Description                   | Min  | Typical | Max  |     |
| --- | -------- | ------ | ----------------------------- | ---- | ------- | ---- | --- |
| 1   | Tx       | Output | Radar signal output           | 0V   | 3.3V    | 3.5V |     |
| 2   | PWM      | Input  | Motor control signal          | 0V   | -       | 3.5V |     |
| 3   | GND      | Power  | Negative power supply         | -    | 0V      | -    |     |
| 4   | P5V      | Power  | Positive pole of power supply | 4.5V | 5V      | 5.5V | n   |

|Baud Rate|Data Bit|Stop Bit|Parity Bit|
|---|---|---|---|
|115200|8 Bits|1|No|