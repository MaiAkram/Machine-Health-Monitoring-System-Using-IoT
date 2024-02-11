# Machine-Health-Monitoring-System-Using-IoT
Machine Health Monitoring System (MHMS) through IoT using Arduino IoT cloud

## Process:
The Process is divided into two parts, where one part considers the machine operation, represented in a DC motor, in addition to the sensors monitoring the operational process. Whereas the second part deals with the total machine operating time, the system alarms, and the lubrication system, represented in a relay which is meant to control the automatic lubricating system valve.
- Firstly, the machine could be turned on or off remotely through the dashboard, with an indication of its status.
- Secondly, data representing machines status are gathered from the sensors, temperature, vibration, and acoustic sensors.
- Accordingly, the collected parameters are compared by the microcontroller, ESP8266 NodeMCU, to threshold values, identified according to the machine operating conditions.
  1) If sound intensity is below 85 dB, then, the maximum exposure time for the workers to the machine is set as 8 hours daily.
  2) If the sound intensity ranges from 85 to 91 dB, then exposure time is specified as 6 h/day.
  3) While it is set as 4h/day for 91 to 95 dB.
  4) And as 3h/day for 95 to 97 dB.
  5) And as 2h/day for more than 95 dB, where the maximum is usually about 100 to 120 dB according to the machine.
- Regarding temperature monitoring for a motor:
  1) If the machine temperature is above 110ºC, then, the machine is diagnosed for possible failure and is shut down automatically with the alarm being turned on.
  2) If the temperature is measure in the range of 80 to 110ºC, then the machine is restrictedly used while being monitored until repair with the alarm still being on.
  3) If the temperature lies within 80 and 55ºC, then the machine is recommended to be scheduled for repair, with a minor problem being expected.
  4) If the machine temperature is below 55ºC and above 45ºC, then the machine is operated unrestrictedly, but maintained whenever possible.
  5) Finally, a working temperature of 45ºC or below is detected, then, the machine is operating in its ambient conditions.
- Subsequently, vibration analysis is performed as follows:
  1) Vibration detection values higher than 7.1 mm/s is diagnosed as a possible damage and the machine is shut down, with the alarm being set.
  2) A vibration value ranging from 4.5 to 7.1 mm/s defines the machine operation in restricted mode under observation.
  3) Whereas a vibration measurement of 3.5 to 4.5 mm/s is identified as a minor problem and the machine is scheduled for maintenance.
  4) A vibration value of 2.3 to 3.5 mm/s sets the machine in an unrestricted operational mode.
  5) While vibrations at 2.3 mm/s or below is defined as ambient conditions.
- If either of the temperature or vibration sensor reading is out of range, then an error is inferred, with a displayed message of “Temperature Sensor not working” or “Vibration Sensor not working”, respectively. In addition, the alarm is turned on and the machine is would operate in monitoring condition, since its true state could not be identified, until the sensors are checked and their operation is corrected.
- If the machine is turned on while in monitoring mode, which is indicated by either a temperature of 80 to 110ºC or a 4.5 to 7.1 mm/s vibration measurement, then the machine is to be kept on for a specified duration before shutting down automatically.
- Regarding the lubricating system, on the one hand, in the first part of the control process, the lubricating is to be operated automatically, where it would be turned on periodically according to a preset time value, namely “Lubricating Period” and would be kept on for a pre-specified amount of time called “Lubrication Done”, whereas each of those two timing values are defined according to the machine operating condition, whether in monitoring mode, normal mode, or faulted sensors mode. On the other hand, in the second part of the process, the lubricating system is to be controlled through the dashboard using a switch with its state being indicated, where it would be turned on manually through the dashboard, and once it is turned on, a timer would count and turn it off automatically according to the “Lubrication Done” value.
- Finally, a dashboard widget is responsible for displaying the total machine operational time since it is turned on, and it is reset whenever the machine is turned off and on again.
- Furthermore, datasets implemented from the recorded information are uploaded to the cloud.
- Cloud could be accessed from smart phone or laptop by supervisors, and machine status could be monitored continuously. Hence, various machine problems could be identified, such as wear, friction, misalignment, need for lubrication, etc.
- Accordingly, the collected data could be integrated with AI and Machine Learning Techniques which enables developing maintenance schedules and taking other appropriate decisions such as machine’s operational conditions adjustments or machine shut down, which takes place automatically in critical situations.

•	Various actions could be taken from the interface, and is transferred to the actuators through Wi-Fi.
