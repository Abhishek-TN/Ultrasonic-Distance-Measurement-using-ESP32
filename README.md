# Ultrasonic Distance Measurement using ESP32

This project utilizes an ESP32 microcontroller to measure distance using an ultrasonic sensor. The ultrasonic sensor calculates distance based on the time taken for a sound wave to travel from the sensor to an object and back. 

## Components Required:
- ESP32 microcontroller
- Ultrasonic sensor (HC-SR04 or similar)
- Buzzer
- Jumper wires

## Circuit Connection:
- Connect the VCC pin of the ultrasonic sensor to the 3.3V output of the ESP32.
- Connect the GND pin of the ultrasonic sensor to the ground (GND) pin of the ESP32.
- Connect the Trig pin of the ultrasonic sensor to pin 7 of the ESP32.
- Connect the Echo pin of the ultrasonic sensor to pin 8 of the ESP32.
- Connect the positive (anode) pin of the buzzer to pin 6 of the ESP32.
- Connect the negative (cathode) pin of the buzzer to the ground (GND) pin of the ESP32.

## Code Explanation:
1. `trigPin` and `echoPin` are defined for the ultrasonic sensor, and `buzz` for the buzzer.
2. `setup()` function initializes the pins for trigPin, echoPin, and the buzzer. Serial communication is also initialized.
3. `loop()` function contains the main code:
    - Triggers the ultrasonic sensor by sending a 10µs pulse to the trigPin.
    - Measures the time taken for the pulse to return using `pulseIn()` function.
    - Calculates distance using the formula: `distance = duration * 0.034 / 2` (since the speed of sound is approximately 34 µs/cm).
    - Prints the measured distance to the Serial Monitor.
    - If the distance is greater than 20 cm, it turns on the buzzer; otherwise, it turns off the buzzer.
    - Delays for 1 second before repeating the process.

## Running the Code:
1. Connect the components as per the circuit connection.
2. Upload the provided code to your ESP32 microcontroller using the Arduino IDE or any other compatible development environment.
3. Open the Serial Monitor to view the measured distance.
4. Observe the buzzer indicating proximity when an object is detected within 20 cm.

## Notes:
- Ensure proper power supply to the components to avoid erratic behavior.
- Adjust the threshold distance (currently set to 20 cm) as per your requirements.
- Use appropriate precautions while working with electrical components.
- Experiment with different distances and adjust the code accordingly for your specific application.
