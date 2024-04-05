###  DATE: 05.04.2024

###  NAME: SREEKUMAR S
###  ROLL NO: 212223240157
###  DEPARTMENT: AIML
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```
int enable=3;
int input1=5;
int input2=6;

void setup()
{
  pinMode(enable, OUTPUT);
  pinMode(input1, OUTPUT);
  pinMode(input2, OUTPUT);
}

void loop()
{
  analogWrite(enable, 255);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(input1, LOW);
  digitalWrite(input2, HIGH);
  delay(7000); // Wait for 7000 millisecond(s)
}
```
### OUTPUT
## CIRCUIT DIAGRAM:
![Screenshot 2024-04-05 160654](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151705853/94f4d0fa-b11d-43d0-8608-2604ecf23922)
## SCHEMATIC DIAGRAM:
![Screenshot 2024-04-05 160918](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151705853/317d06df-210e-400c-921c-12a69b8db86b)


### GRAPH AND TABULATION 
![Screenshot 2024-04-05 161047](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151705853/0f598764-13c8-48ab-a718-ac0477529a5f)
![Screenshot 2024-04-05 161033](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151705853/90bb1f27-787c-4fc6-a67e-cbac7772d4e3)




### RESULTS AND DISCUSSION 
Thus we have controlled the speed and the direction of a DC motor using L293D driver ic( H- bridge)

