# IoT-based-fire-alert-system

int red_led_pin = A2; #connect red led to the A2 pin of Arduino

int green_led_pin = A1; #connect green led to the A1 pin of Arduino
 
int buzzer_pin = 10; #connect buzzer to the 10 pin of Arduino

int smoke_sensor_pin = A0; #connect smoke sensor to the A0 pin of Arduino

void setup()

{
  pinMode(red_led_pin, OUTPUT);

  pinMode(green_led_pin, OUTPUT);

  pinMode(buzzer_pin, OUTPUT);

  pinMode(smoke_sensor_pin, INPUT);

}

void loop() 

{
   int analogSensor = analogRead(smoke_sensor_pin);
   

  if (analogSensor > 200)

  {

    digitalWrite(red_led_pin, HIGH);

    digitalWrite(green_led_pin, LOW);

    tone(buzzer_pin,1000,200);

  }
  
   else

  {

    digitalWrite(red_led_pin, LOW);

    digitalWrite(green_led_pin, HIGH);

    noTone(buzzer_pin);

  }
 

}
