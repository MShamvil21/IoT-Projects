# Problem Statement
As we are starting to learn how to live with Coronavirus, still we should take maximum precaution.To avoid contact with the doors of the house design an
Arduino circuit for **Automatic  Door opener** with a LED Matrix displaying the Welcome Greetings
# Circuit
![ADO](https://user-images.githubusercontent.com/85311689/151153818-01ec301c-cca8-4f89-9b38-9ab0a36fbd96.png)
# Code
~~~
#include<Servo.h>
int trigPin=10;
int echoPin=11;
Servo Door;
long timespan; //Time taken to recieve reflected wave back
long dist; // Distance between the object and  sensor
int pos; //Position of Servo motor
void setup()
{
  Door.attach(4);
  pinMode(trigPin,OUTPUT);
  pinMode(echoPin,INPUT);
  delay(100);
}

void loop()
{
  digitalWrite(trigPin,LOW);
  delayMicroseconds(5);
  digitalWrite(trigPin,HIGH);
  delayMicroseconds(15);
  timespan=pulseIn(echoPin,HIGH);
  dist=(timespan*0.034)/2;
  if(dist<100){
    for(pos=0;pos<=90;pos++){
      Door.write(pos);
      delay(10);
    }
    delay(1000);
    for(pos=90;pos>=0;pos--){
      Door.write(pos);
        delay(10);
    }
    delay(1000);
  }  
}
~~~
# TinkerCad Circuit Link
[Automatic Door Operner with LED Matrix](https://www.tinkercad.com/things/ehqf3cyllm3)

# Further reading

We can add a Welcome message using LED matrix.

[Led_matrix](https://www.tinkercad.com/things/b7Uc3U3CU6y)

[Multiplexing theory](http://lednique.com/display-technology/multiplexed-display/#:~:text=Multiplexing%20is%20a%20technique%20used%20to%20connect%20devices,popular%20due%20to%20low%20cost%20and%20high%20brightness.)
