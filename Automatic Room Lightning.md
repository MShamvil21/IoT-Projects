# Problem Statement

High electricity consumption is a major problem in our homes ,school and offices.To reduce the electricity consumption design a **Automatic Room Lightning System** using Arduino and sensors mentioned below. Light should only turn on when there is movement in the targeted area and should remain off when daylight intensity is high.

# Circuit
![PS1](https://user-images.githubusercontent.com/85311689/149882941-9f5ff0b8-e3a2-4cb7-bee0-2a1a8162726a.png)
```
# Code

int PIRSensorVal;
int LightSensorVal=0;

void setup()
{
pinMode(A0, INPUT);
pinMode(2, INPUT);
pinMode(8, OUTPUT);
Serial.begin(9600);
}

void loop(){
LightSensorVal=analogRead(A0);
PIRSensorVal= digitalRead(2);
 
if (LightSensorVal < 700){
  if (PIRSensorVal==1){
      digitalWrite(8,HIGH);
      delay(1000);
    } else{ digitalWrite(8,LOW);
            delay(1000);
          }
  } 
   else
  {
   digitalWrite(8,LOW);
   Serial.println(LightSensorVal);
   delay(300);
  }
}
```
# TinkerCad Circuit Link
[Automatic Room Lightning Circuit](https://www.tinkercad.com/things/jlIWEJ4P076)
