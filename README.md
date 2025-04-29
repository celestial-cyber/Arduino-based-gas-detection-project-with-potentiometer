Gas Detection Simulation with Arduino and Potentiometer
This project simulates a gas detection system using an Arduino, a potentiometer, and a temperature sensor. Instead of using a real gas sensor, a potentiometer is employed to simulate varying gas levels, allowing for hands-on experimentation and understanding of sensor-based systems.

How It Works:
The system performs two key tasks:
Temperature Monitoring: The temperature sensor (connected to analog pin A1) reads the current temperature and converts it into a voltage signal. This signal is processed by the Arduino to compute the temperature in Celsius. If the temperature exceeds a predefined threshold, an LED connected to pin 13 is turned on as a visual alert for high temperature.
Simulated Gas Detection: The potentiometer (connected to analog pin A0) simulates the gas sensor. The potentiometer's resistance value is read as an analog input, which is used to simulate gas levels. When the potentiometer value exceeds a certain threshold, a buzzer connected to pin 7 is activated as an audio alert for potential gas detection.

Code Explanation:
The Arduino code processes inputs from the temperature sensor and the potentiometer, then takes actions based on the sensor readings.

Temperature Calculation: The temperature is calculated from the analog reading of the temperature sensor using the formula:
𝑉𝑜𝑢𝑡1=(𝑉𝑜𝑢𝑡/1023.0)×5000
Vout1 =(1023.0/Vout)×5000
Where 
𝑉𝑜𝑢𝑡: Vout is the analog reading (0-1023) and 𝑉𝑜𝑢𝑡1 is the corresponding voltage value (0-5000 mV). The temperature in Celsius is then calculated with:
𝑇𝑒𝑚𝑝=(𝑉𝑜𝑢𝑡1−500)/10

​
 Where 500 is the base voltage (corresponding to 0°C), and 10 is the sensor's scaling factor (each 10 mV corresponds to a 1°C change).
Gas Level Detection (Simulated via Potentiometer): The potentiometer value is read as an analog input from pin A0. If the potentiometer reading exceeds a threshold (set to 100 in the code), the buzzer is triggered to simulate a high gas level.

Code Behavior:
LED Alert for Temperature: When the temperature exceeds 20°C, the LED lights up to signal an abnormal temperature condition.
Buzzer Alert for Gas: If the potentiometer value exceeds the threshold (100), the buzzer activates, simulating high gas levels.
Serial Monitor Output: The system prints both the temperature and simulated gas sensor values on the Serial Monitor for real-time tracking.

Features:
Simulated Gas Detection: The potentiometer simulates gas detection by adjusting its value.
Temperature Monitoring: The system continuously monitors and alerts when the temperature exceeds a set limit.
Real-time Feedback: Both temperature and simulated gas levels are displayed on the Serial Monitor.
Visual and Audio Alerts: An LED and buzzer provide immediate feedback based on sensor readings.

Applications:
This project introduces sensor-based systems by teaching how to interface sensors with an Arduino and trigger outputs based on input conditions. It can be expanded to use real gas sensors and more complex alert systems for environmental monitoring.

