# Starbie Controller

I am building the tutorial Starbie to learn more about PCB design and building. I'm building my Starbie in the shape of a controller. I designed my own little character (40x40 pixels) with its own animations. You can see a small picture of it above the PCB screenshot, or look at all of the PNGs uploaded in the main branch. The controls are based on the default Starbie code, with my own animations attached (see **Controls** below).

The Starbie has 2 buttons for interacting with menus, a temperature/humidity sensor for sensing the environment, and a gyro sensor that also lets you interact with the character to make the Starbie more immersive. There is also a 0.96" OLED display for showing the character and menus, and lastly the ESP32 that controls everything. The full parts list is in the BOM table below.

## Controls

| Input | Where | What it does |
|:------|:------|:-------------|
| **Button 1** (XIAO D2) | Pet / stats screen | Opens the radial menu. The way you're holding the controller when you press it becomes the "center" for that menu. |
| **Button 1** | Radial menu | Confirms the highlighted action and returns to the pet. If the ball is still in the center (nothing highlighted), nothing happens and the menu stays open. |
| **Button 2** (XIAO D3) | Any screen | Toggles the stats screen (Joy, Energy, Fullness bars + temperature and humidity from the DHT11). It only shows values and never changes the pet. Pressing it in the menu leaves the menu without choosing anything. |
| **Tilt** | Radial menu | Moves the ball like an air mouse. Tilt up, right, down or left to highlight the action on that side. A small dead zone in the middle means nothing is selected. |
| **Shake** | Pet screen | Wakes Starbie up if it's napping and plays a dizzy animation. Joy +5, Energy −2, Fullness −1. |

### Menu actions

| Direction | Action | Joy | Energy | Fullness | Animation |
|:---------:|:-------|----:|-------:|---------:|:----------|
| Up | **NAP** | +1 | +18 | −4 | Falls asleep for 48 s with floating Zs (shake to wake early) |
| Right | **PLAY** | +12 | −9 | −5 | Runs two fast laps across the screen with hearts |
| Down | **FEED** | +3 | +2 | +18 | Wiggles and jumps |
| Left | **PET** | +7 | 0 | 0 | Jumps and emits hearts |

All stats go from 0 to 100. They only change when you choose an action or shake Starbie, so nothing drains while it sits on your desk. Stats are saved to flash and stay after you power off. When nothing else is happening, Starbie walks back and forth across the screen.

## BOM

| Item | Qty | Supplier | Cost/item | Total Cost | Link |
|:-----|:---:|:---------|----------:|-----------:|:-----|
| ESP32-C3 XIAO Seeed Studio | 1 | electro:kit | $10.85 | $10.85 | [Link](https://www.electrokit.com/en/seeed-studio-xiao-esp32c3) |
| Cherry MX blue switch | 2 | electro:kit | $1.95 | $3.90 | [Link](https://www.electrokit.com/en/cherry-mx-blue-switch) |
| Carbon film resistor 0.25W 10kΩ | 10 | electro:kit | $0.10 | $1.00 | [Link](https://www.electrokit.com/motstand-kolfilm-0.25w-10kohm-10k) |
| Temp/moisture sensor DHT11 | 1 | electro:kit | $3.92 | $3.92 | [Link](https://www.electrokit.com/en/temp/fuktsensor-dht11) |
| 6-axis IMU accelerometer and gyro MPU6050 (I2C) | 1 | electro:kit | $7.23 | $7.23 | [Link](https://www.electrokit.com/en/mpu-6050-accelerometer-3-axel-gyro-monterad-pa-kort) |
| 0.96" I2C OLED white | 1 | Sizable | $5.70 | $5.70 | [Link](https://sizable.se/product/1081/0.96-I2C-OLED-Vit) |
| PCB | 1 | JLCPCB | $5.20 | $5.20 | [Link](https://jlcpcb.com) |
| Keycaps | 2 | Own (unknown brand) | $0.00 | $0.00 | – |
| Estimated total shipping | 1 | | | $5.52 | |
| **Total** | | | | **$43.32** | |

<img width="40" height="40" alt="Starbie character" src="https://github.com/user-attachments/assets/0f254c8e-50cf-4dc6-8a5f-9e736b18d0e6" />
<img width="947" height="644" alt="PCB screenshot" src="https://github.com/user-attachments/assets/1950006d-4c2d-46c2-ac74-049ac98b3cca" />
<img width="701" height="437" alt="PCB render 1" src="https://github.com/user-attachments/assets/9be12f74-e821-42d0-93ac-7d4a9a0eea2d" />
<img width="717" height="441" alt="PCB render 2" src="https://github.com/user-attachments/assets/cb1e1a8e-3afc-48e2-85ef-0d623d8559fe" />
