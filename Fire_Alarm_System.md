# Problem Statement

Disaster Management is one of the main aspect when we wish to build smart homes. The major source of disaster in our homes is our kitchen.Design a Fire Alarm circuit which can predict the increase in temperature and accumulation of harmful gases  in our kitchens and prevent any kind of disaster.

# Circuit


![7CuDZTelB7](https://user-images.githubusercontent.com/85684926/151136560-b80f34b8-cda1-4a6c-abea-9c82bbcc997b.gif)

```
// C++ code
//
void setup()
{
  pinMode(A5, INPUT);
  Serial.begin(9600);
  pinMode(2,OUTPUT);
  pinMode(3,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  int a = analogRead(A5);
  int b = analogRead(A0);
  float temp_cel = -40 + (b-20)/338.0*165;
  //Serial.println(a);
  //Serial.println(b);
  if(a>274)
    digitalWrite(6,HIGH);
  if(a>300)
    digitalWrite(5,HIGH);
  if(a>400)
    digitalWrite(4,HIGH);
  if(a>500)
  {
    digitalWrite(3,HIGH);
    Serial.println(temp_cel);
  }
  if(a>600)
    digitalWrite(2,HIGH);
  delay(100);
  digitalWrite(2,LOW);
  digitalWrite(3,LOW);
  digitalWrite(4,LOW);
  digitalWrite(5,LOW);
  digitalWrite(6,LOW);
  
}
```
# TinkerCad Circuit Link
[Fire_Alarm_System_Circuit](https://www.tinkercad.com/things/1If2sjN5ir9)

# Further reading

[Gas sensors explained](https://components101.com/articles/introduction-to-gas-sensors-types-working-and-applications)

[MQ2 gas sensor datasheet](http://gas-sensor.ru/pdf/combustible-gas-sensor.pdf)

[Temperature sensor working](https://www.tneutron.net/mikro/working-principle-sensor-lm35/#:~:text=Working%20Principle%20Sensor%20LM35%201%20The%20ambient%20temperature,output%20voltage%20changes.%203%20In%20the%20series%20LM35)

[LM35 datasheet](https://www.ti.com/lit/ds/symlink/lm35.pdf)


