# Automatic-Motion-Activated-Security-using-PIR-Sensor

## AIM:

To detect motion using a PIR sensor connected to an Arduino and trigger an LED (using the built-in LED) when motion is sensed.

## Hardware / Software Tools required:

1. Arduino Uno R3 – 1 No
2. PIR Sensor – 1 No
3. LED (in-built on Arduino pin 13) – 1 No
4. 220-ohm resistor – 1 No (used with external LED if necessary)
5. Breadboard – 1 No
6. Jumper wires – As required
7. USB Cable – 1 No (for uploading code and powering Arduino)
8. Computer with Tinkercad or Arduino IDE installed

## Theory:

Passive Infrared (PIR) sensors are electronic devices that detect motion by sensing infrared radiation emitted by objects. Every object with a temperature above absolute zero emits infrared radiation. The PIR sensor detects this radiation and can sense motion when a warm object, such as a human body, passes within its detection range. The sensor contains a pair of pyroelectric sensors housed under a Fresnel lens, which focuses the infrared signals onto the sensor surface. When the infrared levels change rapidly between the two pyroelectric sensors—such as when a person walks by—the sensor outputs a HIGH signal indicating motion detection.

PIR sensors are widely used in motion detection systems, security alarms, automatic lighting systems, and smart surveillance. They are popular due to their low power consumption, affordability, and ease of integration with microcontrollers such as the Arduino Uno. The sensor typically has three pins: VCC (power), GND (ground), and OUT (signal). When idle, the output pin remains LOW. Once motion is detected, the sensor sends a HIGH signal to the microcontroller, which can be used to trigger a response such as turning on an LED or activating an alarm.

In this experiment, the PIR sensor is connected to an Arduino Uno board. The VCC pin of the sensor is connected to the 5V supply of the Arduino to power the sensor. The GND pin is connected to the Arduino’s ground. The OUT pin is connected to a digital input pin (pin 2 in this case) of the Arduino. The Arduino continuously monitors the state of the signal pin. If the signal pin goes HIGH, it means the sensor has detected motion, and the Arduino is programmed to turn ON the built-in LED on pin 13. If no motion is detected, the signal remains LOW, and the LED is turned OFF.

## Circuit Diagram:

<img width="1210" height="786" alt="image" src="https://github.com/user-attachments/assets/9cf815ac-f392-43b8-bac7-d9b3e1a10480" />

## Procedure:

---

#### Step 1: Set Up the Tinkercad Environment

1. Log in to [TinkerCAD](https://www.tinkercad.com) in your browser.
2. In the dashboard, click **“Circuits” → “Create New Circuit.”**
3. This opens a new simulation workspace.

---

#### Step 2: Add Components to the Circuit

1. **Arduino UNO:** Drag and drop the Arduino UNO R3 board into the workspace.
2. **PIR Sensor:** Search and add the PIR motion sensor from the components panel.
3. **LED (optional):** You can use the built-in LED on pin 13 or add an external LED.
4. **Resistor:** Add a **220 Ω resistor** in series with the external LED to limit current.
5. **Jumper Wires:** Use wires to connect all components as shown in the circuit diagram.

---

#### Step 3: Connect the PIR Sensor to Arduino UNO

1. **PIR Sensor Pin Connections:**

   * **VCC** → Arduino **5V**
   * **GND** → Arduino **GND**
   * **OUT** → Arduino **Digital Pin 2**
2. **Optional LED Wiring (if external LED used):**

   * LED **Anode (+)** → Arduino **Pin 13** via **220 Ω resistor**
   * LED **Cathode (–)** → Arduino **GND**

---

#### Step 4: Write the Arduino Code

1. Click **Code → Text Mode** in the Tinkercad workspace.
2. Write or paste the C/C++ code for motion detection using the PIR sensor.
3. The code should read the PIR sensor output and control the LED accordingly.

---

#### Code:

```c
int buttonState = 0;

void setup()
{
  pinMode(2, INPUT);
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop()
{
  buttonState = digitalRead(2);
  if (buttonState == HIGH)
  {
    digitalWrite(LED_BUILTIN, HIGH);
  }
  else
  {
    digitalWrite(LED_BUILTIN, LOW);
  }
  delay(10);
}
```

---

#### Step 5: Simulate the Circuit

1. Click **“Start Simulation.”**
2. Move the **virtual motion object (blue ball)** near the PIR sensor in Tinkercad.

   * **LED ON:** Motion detected
   * **LED OFF:** No motion
3. Observe the serial monitor for “Motion Detected” or “No Motion” messages.

---

#### Step 6: Troubleshoot and Refine

1. Verify all wiring connections match the circuit diagram.
2. Ensure the **OUT** pin of the PIR sensor is correctly connected to **D2** on Arduino.
3. Check for syntax errors in the code.
4. Adjust the PIR sensor’s angle or detection range if needed.

---

#### Step 7: Save Your Work

1. Click **“Stop Simulation”** after completing testing.
2. Click **“Save”** to store your circuit and code for future use.

---

# Output:

<img width="1228" height="982" alt="image" src="https://github.com/user-attachments/assets/9b73c7bf-159e-4bde-94aa-f77683bfff53" />

---

# Result:

The PIR sensor successfully detected motion and triggered the Arduino to turn ON the built-in LED. The LED remained OFF when no motion was present, confirming correct circuit and code functionality.

---
