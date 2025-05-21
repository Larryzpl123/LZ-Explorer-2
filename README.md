# LZ-Explorer-2 Foam Plane Modification Guide

## Key Points
- Research indicates that modifying a foam hand-thrown airplane requires careful integration and testing of components.
- Safety, weight management, and balance are essential for achieving successful flight.
- Evidence supports using an ESP32 for control, with Bluetooth or Wi-Fi enabling interaction via a mobile app.

## Materials and Setup
The LZ-Explorer-2 project modifies a 17.5-inch foam airplane using components such as a 3.7V lithium battery, a 20A brushed ESC, 9g micro servos, and an ESP32 for control. Ensure all materials listed in the table below are prepared for a seamless modification process.

| Item                                                 | Quantity | Detailed Function                                                                                                   |
|------------------------------------------------------|----------|---------------------------------------------------------------------------------------------------------------------|
| 17.5-inch Hand-Thrown Foam Airplane                  | 1        | Lightweight foam fuselage serving as the structural base of the airplane.                                           |
| 3.7V Lithium Battery                                 | 1        | Powers the ESC, motors, servos, ESP32, and FPV camera; 1000mAh capacity ensures stable power delivery.             |
| 20A Brushed ESC                                      | 1        | Regulates the speed of two 8520 hollow cup motors; includes BEC for 5V power output.                               |
| 9g Micro Servos                                      | 4        | Manage control surfaces (elevon/aileron, elevator, rudder, direction adjustment); require PWM signals.              |
| Servo Control Board                                  | 1        | Provides precise PWM signal control for synchronized servo movements.                                               |
| Servo Mounts (Brackets)                              | 4        | Secure servos to control surfaces, with spares for replacements.                                                    |
| 8520 Hollow Cup Motors                               | 4        | Deliver thrust for propulsion.                                                                                      |
| 58mm Propellers                                      | 4        | Convert motor rotation into forward thrust, paired with the motors.                                                 |
| Arduino/ES Development Board (e.g., ESP32-WROOM-32)  | 1        | Central control unit; receives Bluetooth signals and generates PWM for ESC and servos.                             |
| FPV Camera with Transmitter                          | 1        | 5.8GHz camera for real-time video streaming to a ground monitor or computer.                                        |
| FPV Video Receiver                                   | 1        | Receives video signals for live monitoring on a computer or display.                                               |
| Hot Glue Gun / Fiber Adhesive Tape                   | 1        | Secures components like motors and servos for stability during flight.                                              |
| Utility Knife                                        | 1        | Cuts foam or materials to adjust fuselage shape and dimensions.                                                     |
| Wire / Rope                                          | 10+      | Reinforces the structure and connects components for added stability.                                               |
| Jumper Wires and Connectors                          | 30+      | Connect ESP32 PWM pins to ESC and servos for reliable signal transmission.                                          |
| Android Phone                                        | 1        | Ideally foldable with split-screen capability for viewing camera feed and control; use `ESP-Drone_0.7.3.apk` for testing. |

## Steps to Follow
Modify your foam airplane by following these steps:
- **Prepare the Airframe**: Cut or adjust the foam to accommodate motors, servos, and other components.
- **Install Motors and Propellers**: Securely attach motors and propellers to the airframe.
- **Mount Servos**: Connect servos to control surfaces using mounts and linkages.
- **Set Up the ESC**: Link the ESC to the motors and battery for power distribution.
- **Integrate the ESP32**: Connect the ESP32 to the ESC and servos for control functionality.
- **Add the FPV Camera**: Install the camera and transmitter, ensuring proper power and connections.
- **Wire Components**: Use jumper wires to connect all parts, verifying correct wiring.
- **Program the ESP32**: Upload control code, setting it up for Bluetooth or Wi-Fi commands.
- **Ground Test**: Check motor response, servo movement, and FPV feed before flight.
- **Flight Test**: Conduct initial flights in a safe area, adjusting trims and settings as needed.

---

# Survey Note: Detailed Analysis and Implementation Guide for LZ-Explorer-2 Foam Plane Modification

This section offers an in-depth guide to transform the LZ-Explorer-2 hand-thrown foam airplane into a remote-controlled, FPV-capable aircraft using an ESP32, complete with reminders, procedures, code, and references.

## Project Context and Materials
The LZ-Explorer-2 project converts a 17.5-inch foam airplane into an RC plane with FPV features. Key components include a 3.7V 1000mAh lithium battery, a 20A brushed ESC with BEC, four 9g micro servos, four 8520 hollow cup motors with 58mm propellers, and an ESP32-WROOM-32 board. Additional tools and items like an FPV camera, servo control board, hot glue gun, and utility knife complete the setup. An Android phone with split-screen capability is recommended, using the `ESP-Drone_0.7.3.apk` app for control and monitoring.

References include a primary Bilibili tutorial ([Bilibili Video](https://www.bilibili.com/video/BV1gL41147GR)), a YouTube ESP32 drone video ([YouTube Video](https://www.youtube.com/watch?v=V_mZsiZcy7s)), and additional Bilibili videos on airplane modifications ([Bilibili Video](https://www.bilibili.com/video/BV1Bg41137GT), [Bilibili Video](https://www.bilibili.com/video/BV1Su4y1w7oN/)).

## Reminders for Safe and Effective Modification
Consider these critical points during modification:
- **Safety**: Handle batteries, electronics, and propellers carefully to prevent injury.
- **Weight Management**: Keep added weight minimal (target ~50g total flying weight) to maintain foam airplane balance.
- **Balance and CG**: Adjust the center of gravity to 20%-25% of chord length, using battery placement for tuning.
- **Component Testing**: Verify motors, servos, and ESC functionality individually before assembly.
- **Secure Connections**: Use jumper wires (30+) and reinforce with glue or tape to ensure reliability.
- **Calibration**: Follow ESC and servo calibration steps (e.g., ESC sequence: 0, 180, 0) for smooth operation.
- **FPV Camera Positioning**: Mount the camera for a clear view, securely powered and connected.
- **Local Regulations**: Check laws for RC and FPV flight compliance.
- **Decalage and Incidence**: Set wing-stabilizer angle near zero, with 1-2° motor downthrust.
- **ESC Cooling**: Provide ventilation to prevent ESC overheating.
- **Elevator Angle**: Adjust glider-specific up angles for powered flight.

These tips draw from community advice, such as Reddit discussions ([Reddit Post](https://www.reddit.com/r/RCPlanes/comments/bx53wn/turning_foam_glider_into_rc_plane/)).

## Detailed Procedures for Modification
Follow these detailed steps:
1. **Prepare the Airframe**: Cut foam with a utility knife to fit components, reinforcing with wire/rope (10+).
2. **Install Motors and Propellers**: Mount four 8520 motors with 58mm propellers, securing with glue/tape.
3. **Mount Servos**: Attach four 9g servos for elevon/aileron, elevator, rudder, and direction, using brackets.
4. **Set Up the ESC**: Connect the 20A ESC to motors and battery, ensuring BEC powers other components.
5. **Integrate the ESP32**: Wire the ESP32 to the ESC and servos via PWM pins, using 30+ jumper wires.
6. **Add the FPV Camera**: Install the 5.8GHz camera and transmitter, connecting to the battery or ESP32.
7. **Wiring**: Ensure correct power (3.5V~3.0V) and signal connections with insulated jumper wires.
8. **Programming**: Upload ESP32 code for Bluetooth ("ESP32_RC_Plane") or Wi-Fi (SSID: ESP-DRONE_XXXX, PASSWORD: 12345678).
9. **Testing**: Ground-test motors, servos, and FPV, adjusting settings like RSSI (-85 dBm) and voltage alerts (<3.7V).
10. **Flight Testing**: Launch at 60% throttle, level at 20-25%, and adjust CG/elevator for smooth flight.

These steps are inspired by guides like the Instructables WiFi plane project ([Instructables Guide](https://www.instructables.com/WIFI-CONTROLLED-RC-PLANE/)).

## Code Implementation for Control
Below is a basic Bluetooth control code for the ESP32, managing the ESC and servos:

```cpp
#include <BluetoothSerial.h>
#include <ESP32Servo.h>

// Define pins
#define ESC_PIN 18
#define SERVO1_PIN 19
#define SERVO2_PIN 21
#define SERVO3_PIN 22
#define SERVO4_PIN 23

BluetoothSerial SerialBT;
Servo esc;
Servo servo1, servo2, servo3, servo4;

void setup() {
  Serial.begin(115200);
  SerialBT.begin("ESP32_RC_Plane"); // Bluetooth device name

  // Attach ESC and servos
  esc.attach(ESC_PIN);
  servo1.attach(SERVO1_PIN);
  servo2.attach(SERVO2_PIN);
  servo3.attach(SERVO3_PIN);
  servo4.attach(SERVO4_PIN);

  // Initialize ESC
  esc.write(0);
  delay(1000);
  esc.write(180);
  delay(1000);
  esc.write(0);
}

void loop() {
  if (SerialBT.available()) {
    String command = SerialBT.readStringUntil('\n');
    // Example format: "THR:50,SRV1:90,SRV2:90,SRV3:90,SRV4:90"
    int thr = parseValue(command, "THR");
    int srv1 = parseValue(command, "SRV1");
    int srv2 = parseValue(command, "SRV2");
    int srv3 = parseValue(command, "SRV3");
    int srv4 = parseValue(command, "SRV4");

    esc.write(thr);
    servo1.write(srv1);
    servo2.write(srv2);
    servo3.write(srv3);
    servo4.write(srv4);
  }
}

int parseValue(String command, String key) {
  int start = command.indexOf(key + ":") + key.length() + 1;
  int end = command.indexOf(",", start);
  if (end == -1) end = command.length();
  String valueStr = command.substring(start, end);
  return valueStr.toInt();
}
```

For Wi-Fi, adapt the ESP-Drone firmware ([GitHub - ESP-Drone](https://github.com/espressif/esp-drone)) and use the `ESP-Drone_0.7.3.apk` ([ESP-Drone APK](https://www.pgyer.com/a27L)).

## Additional Resources / Citations
- **Main Tutorial**: [Bilibili Video](https://www.bilibili.com/video/BV1gL41147GR) - DIY foam airplane modification.
- **ESP32 Drone**: [YouTube Video](https://www.youtube.com/watch?v=V_mZsiZcy7s) - Smallest ESP32 drone with phone control.
- **Modification Tutorials**: [Bilibili Video](https://www.bilibili.com/video/BV1Bg41137GT), [Bilibili Video](https://www.bilibili.com/video/BV1Su4y1w7oN/) - Airplane and foam board guides.
- **Technical Resources**: [ESP-Drone Documentation](https://docs.espressif.com/projects/espressif-esp-drone/en/latest/index.html), [Instructables Guide](https://www.instructables.com/WIFI-CONTROLLED-RC-PLANE/), [GitHub - ESP32 RC Plane](https://github.com/lnxdxtf/esp32-rcplane), [HowToMechatronics Tutorial](https://howtomechatronics.com/projects/arduino-rc-airplane-diy/).

## Other Key References
- [Bilibili Video](https://www.bilibili.com/video/BV1gL41147GR)
- [YouTube Video](https://www.youtube.com/watch?v=V_mZsiZcy7s)
- [Bilibili Video](https://www.bilibili.com/video/BV1Bg41137GT)
- [Bilibili Video](https://www.bilibili.com/video/BV1Su4y1w7oN/)
- [GitHub - ESP-Drone](https://github.com/espressif/esp-drone)
- [Instructables Guide](https://www.instructables.com/WIFI-CONTROLLED-RC-PLANE/)
- [GitHub - ESP32 RC Plane](https://github.com/lnxdxtf/esp32-rcplane)
- [HowToMechatronics Tutorial](https://howtomechatronics.com/projects/arduino-rc-airplane-diy/)
- [ESP-Drone APK](https://www.pgyer.com/a27L)
- [Reddit Post](https://www.reddit.com/r/RCPlanes/comments/bx53wn/turning_foam_glider_into_rc_plane/)
- [ESP-Drone Documentation](https://docs.espressif.com/projects/espressif-esp-drone/en/latest/index.html)
