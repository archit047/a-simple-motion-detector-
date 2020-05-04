# a-simple-motion-detector-
a simple project based on iot used to detect the motion
a-simple-motion-detector-
a simple project based on iot used to detect the motion.
PIR-Sensor
A passive infrared sensor (PIR sensor) is an electronic sensor that measures infrared (IR) light radiating from objects in its field of view. They are most often used in PIR-based motion detectors. PIR sensors are commonly used in security alarms and automatic lighting applications. PIR sensors detect general movement, but do not give information on who or what moved. For that purpose, an active IR sensor is required.
CODE
int ledPin = 8; int inputPin = 4; int pirState = LOW; int val = 0; void setup() { // put your setup code here, to run once:
pinMode(ledPin, OUTPUT); pinMode(inputPin, INPUT); // declare Sensor as input Serial.begin(9600);
}
void loop() { // put your main code here, to run repeatedly: val = digitalRead(inputPin); // read input value if (val == HIGH) { // check if the input is HIGH digitalWrite(ledPin, HIGH); // turn LED ON if (pirState == LOW) {
// we have just turned on Serial.println("Motion detected"); // We only want to print on the output change , not State pirState = HIGH; delay(100); } } else { digitalWrite(ledPin, LOW); // turn LED OFF if (pirState == HIGH) { // We have just turned off Serial.println("Motion ended!"); // we only want to print the output change not State pirState = LOW; delay(100); } } }
       # CIRCUIT CONNECTIONS WITH ARDUINO AND PIR SENSOR!!!
       
                          Arduino------|--------PIR
                          5V-----------|--------Vcc
                          2------------|---------Vo
                          GND----------|--------GND

