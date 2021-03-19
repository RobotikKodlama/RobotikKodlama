/*
* 1 tane RGB ledi döngüye sokarak birçok renk elde etmek amacıyla. Sıcaklık seviye göstergeleri gibi durumlarda kullanılablir. 
Arduino Nano ile devreyi kurdum. Nano'nun Anolog PWM çıkışlarını bulmak biraz oldu ama D3 , D5  D6 çıkışlarını RGB olrak kullandım. Anot zaten 5V idi. ledleri 220ohm direnç ile koruduk
*/

const int k_led = 3;
const int y_led = 5;
const int m_led = 6;

void setup()

{
  Serial.begin(9600); 
  pinMode(k_led, OUTPUT);
  pinMode(y_led, OUTPUT);
  pinMode(m_led, OUTPUT);
}

void loop(){
for(int k=1; k<=255; k=k+20){
  for(int y=1; y<=255; y=y+20){
    for(int m=1; m<=255; m=m+20){

  analogWrite(k_led, k); 
  analogWrite(y_led, y);
  analogWrite(m_led, m);
  Serial.print (k);   Serial.print (" - ");
  Serial.print ( y);    Serial.print (" - ");
  Serial.println (m) ;
    delay(20);
      }
    }
  }
}
