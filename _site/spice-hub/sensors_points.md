//when the senors sense something, one adds four points and one subtracts two points

#include <Pinball.h>


Pb_display disp(10, 8, 9);  // (datapin, clkpin, latchpin)

Pb_muxin mymux(2, 3, 4, 7); // (pinA, pinB, pinC, COMpin)

int num, flag0, flag1, flag2;

Pb_switch mysw0(50), mysw1(50), mysw2(50);

void setup() {

  disp.print_number(0);
  
  num = 0;
  flag0 = 0; flag1 = 0; flag2 = 0;
  
 // Serial.begin(9600);

}


void loop() {

  readinputs();       // Read all the input sensors
  dologic();          // Perform logical operations
  writeoutputs();     // Control all output components
  
}


void readinputs() {

  flag0 = 0; flag1 = 0; flag2 = 0;
  
  // Use flags to record which switches have been pushed
  //flag0 = mysw0.pushed( mymux.probe(0) );//
  mymux.probe(0);
  digitalWrite(7, LOW);
  delay(1);
  flag0 = mysw0.pushed(!digitalRead(7));
  //Serial.println(digitalRead(7));
  digitalWrite(7, HIGH);
  //flag1 = mysw1.pushed( mymux.probe(1) );
   mymux.probe(1);
  digitalWrite(7, LOW);
  delay(1);
  flag1 = mysw0.pushed(!digitalRead(7));
  //Serial.println(digitalRead(7));
  digitalWrite(7, HIGH);
  flag2 = mysw2.pushed( mymux.probe(2) );  
  
}


void dologic() {
  
  if (flag0 == 1) {   // If switch 0 has been pushed, decrease number
    num = num + 4;
    if (num < 0) {
      num = 0;
    }
  }
  
  if (flag1 == 1) {  // If switch 1 has been pushed, set number to 50
    num = num - 2;
  }
  
  if (flag2 == 1) {  // If switch 2 has been pushed, increase number
    num = num + 5;
    if (num > 99) {
      num = 99;
    }      
  }
}


void writeoutputs() {

  if ( (flag0 + flag1 + flag2) > 0 ) {  // If at least one switch has been pushed
     disp.print_number(num);            // Output the number to the scoreboard
  }
  
}