# WLED Remote Control for ESP32 using ESP-NOW Protocol

This project allows controlling WLED devices using an ESP32 over the ESP-NOW protocol, mimicking the functionality of a WiZmote. The ESP32 sends commands wirelessly to the WLED device, and the communication operates efficiently without needing to connect to Wi-Fi.

## Features

- **ESP-NOW Protocol**: Utilizes the low-power, fast, and efficient ESP-NOW communication method to control WLED devices.
- **WLED Control**: Commands like turning lights on/off, adjusting brightness, and switching presets are supported.
- **Touch Sensor Integration**: The ESP32 uses a touch sensor (T0) to wake from deep sleep and send control commands to the WLED device.
- **Deep Sleep Mode**: After sending a command, the ESP32 enters deep sleep to significantly reduce power consumption, making it energy-efficient for long-term usage.

## Configuration

1. **Set WLED MAC Address**:
   - Modify the `macAddress[]` variable in the code to match the MAC address of your WLED device.

2. **Set Wi-Fi Channel**:
   - Set the `CHANNEL` constant to the same channel used by your WLED device.

3. **Configure WLED to Listen to ESP-NOW Events**:
   - In the WLED web interface, go to **Config > WiFi setup**.
   - Scroll down to the **Wireless Remote** section.
   - Enable **ESP-NOW Enable Remote** and modify the `Hardware MAC` with the ESP32 MAC address.
  
## Usage
  If everything has been configured correctly, when the T0 pin (GPIO4) is touched in the ESP32, the LEDs configured in WLED will turn on/off.
  The operation can be modified. 

## Available Functionalities

The ESP32 remote control can trigger the following WLED functions using ESP-NOW:

1. **Turn Lights On/Off**: 
   - **Constant**: `ON` (1), `OFF` (2)
   - Tap the touch sensor to toggle the WLED device between on and off states.

2. **Adjust Brightness**:
   - **Constant**: `BRIGHT_UP` (9), `BRIGHT_DOWN` (8)
   - Increase or decrease the brightness of the WLED lights by sending brightness control commands.

3. **Switch Between Presets**:
   - **Constants**:
     - `PRESET_ONE` (16): Send preset one command.
     - `PRESET_TWO` (17): Send preset two command.
     - `PRESET_THREE` (18): Send preset three command.
     - `PRESET_FOUR` (19): Send preset four command.
   - Easily switch between four preset configurations in WLED.

4. **Night Mode**:
   - **Constant**: `NIGHT` (3)
   - Activate night mode to dim the lights to a comfortable level for evening or low-light conditions.

  
