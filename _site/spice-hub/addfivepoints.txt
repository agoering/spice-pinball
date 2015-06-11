// Adds 5 points to the scoreboard when a button is pressed

#include <Pinball.h>

int clkpin2 = 8;      // Clock pin
int latchpin2 = 9;    // Latch pin
int datapin2 = 10;     // Data pin

// Declare scoreboard object named disp 
Pb_display disp(datapin2, clkpin2, latchpin2);

int buttonpin = 3;
Pb_switch bsw(50);

int buttonpin2=4;

int buttonpin3=5;

int num = 0, oldnum = 0;


void setup() {
  // Write a 0 to the display.
  disp.print_number(0);
  
  pinMode(buttonpin, INPUT);
  digitalWrite(buttonpin, HIGH);
  
  pinMode(buttonpin2, INPUT);
  digitalWrite(buttonpin2, HIGH);
  
pinMode(buttonpin3, INPUT);
  digitalWrite(buttonpin3, HIGH);
  
}


void loop() {
  
//  dothis.update();
  readbutton();
  
  writescore(); 
   
}

void readbutton() {
  
  if (bsw.pushed( digitalRead(buttonpin)) ) {
    
    num = num + 5;
  }
    
    if (bsw.pushed( digitalRead(buttonpin2)) ) {
     num = num + 5;
    }


    if (bsw.pushed( digitalRead(buttonpin3)) ) {
      num = num + 5;
   }
}

void writescore() {
 
  if (oldnum != num ) {
     disp.print_number(num);
    oldnum = num;
  } 
}
  