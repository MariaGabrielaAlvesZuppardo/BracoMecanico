#include <ESP32Servo.h>


// inclui bibilioteca do servomotor
//#include <Servo.h> 

// define pinos dos servos
#define pinServ1 16
#define pinServ2 21
#define pinServ3 17
#define pinServ4 22


// nomeia os servos
Servo serv1,serv2,serv3,serv4;



void setup() {

  //inicia o monitor serial
  Serial.begin(9600); 

  // atribui pinos dos servos
  serv1.attach(pinServ1);
  serv2.attach(pinServ2);
  serv3.attach(pinServ3);
  serv4.attach(pinServ4);
  
}

void aciona_motor(Servo* serv_motor, int position_start, int position_end, int velocity)
{
  serv_motor->write(position_start);
  serv_motor->write(position_start);
  delay(300);
  if (velocity > 0)
  {
    for(int pos = position_start; pos <= position_end; pos += velocity){
      serv_motor->write(pos);
      serv_motor->write(pos);
      Serial.println(pos);
      delay (200);
    }
  }
  serv_motor->write(position_end);
  serv_motor->write(position_end);
}

void loop(){

  // posicionamento inicial
  aciona_motor(&serv1, 0, 180, 0);
  
  delay (1000);
  
  aciona_motor(&serv2, 50, 90, 0);
  
  delay (1000);

  aciona_motor(&serv4, 0, 160, 0);
  
  delay (1000); 
   
  //terceira posicao
  aciona_motor(&serv2, 120, 120, 0);
  aciona_motor(&serv3, 0, 0, 0);
  
  delay (1000);
  
  aciona_motor(&serv1, 0, 0, 0);
  
  delay (1000);
  
  aciona_motor(&serv1, 140, 140, 0);

  // tempo de espera para recomeçar
  delay (10000);

}
