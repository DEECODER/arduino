//# arduino
//basic arduino codings
#include <LiquidCrystal.h>
LiquidCrystal lcd(11,10,5,4,3,2);
int val;
int tempPin = 1;

void setup() {
  // put your setup code here, to run once:
lcd.begin (16,2);
}

void loop() {
 val = analogRead(tempPin);
 float mv= (val/1024.0)*5000;
 float cel = mv/10;
 float farh = (cel*9)/5 + 32;
 
 lcd.print("TEMPERATURE=");
 lcd.setCursor(0,1);
 lcd.print(cel);
 lcd.setCursor(5,1);
 lcd.print("*C");
 delay (1000);
 lcd.clear();// put your main code here, to run repeatedly:

}
