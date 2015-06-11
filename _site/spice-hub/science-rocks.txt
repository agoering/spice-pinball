// Flashes LEDs in a scrolling pattern (BOOM)

#include <Pinball.h>

// Connect two 74HC595s' in series
// Connect LEDs with 1k resistors to their outputs

int clkpin = 12;      // Clock pin
int latchpin = 13;    // Latch pin
int datapin = 11;     // Data pin
int numreg = 2;       // Number of shift registers in series

// Declare object named shregs 
Pb_outputs shregs(datapin, clkpin, latchpin, numreg);

byte serdata[2];

int val[] = { 0, 1, 2, 3, 4, 5, 6, 7, 0, 1, 2, 3, 4, 5, 6, 7, 0, 1, 2, 3, 4, 5, 6, 7 };
int time[] = {100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100};

Pb_timedevent flashlights(changeserdata);

Pb_stopwatch mywatch;

int flag, ontime = 100;

void setup() {

 serdata[0] = 0b11111111;
 serdata[1] = 0b11111111; 

 shregs.update(serdata);   // Shifting out the array
 delay(20);

 flag = 0;
 mywatch.start();
 
 pinMode(14, INPUT);
 pinMode(15, INPUT);

}


void loop() {
  flashlights.update();

/* 
 if (mywatch.time() > ontime ) {
   
   mywatch.start();
   changeflag();
   changeserdata(flag);
   shregs.update(serdata);
   
 } 
 */
 if (digitalRead(14) == 1) {
   flashlights.start(val, time, 24);
  
 }
 if (digitalRead(15) == 1) {
   flashlights.start(val, time, 24);
 }
 
}


void changeflag() {
 
 if (flag < 7) { 
  flag = flag + 1;
 } else {
  flag = 0;
 } 
  
}

void changeserdata(int ff) {
  
 if (ff == 0)      { serdata[0] =  0b11111111; serdata[1] = 0b111111111; }
 else if (ff == 1) { serdata[0] =  0b00000010; serdata[1] = 0b00000010; }
 else if (ff == 2) { serdata[0] =  0b00000100; serdata[1] = 0b00000100; }
 else if (ff == 3) { serdata[0] =  0b00001000; serdata[1] = 0b00001000; }
 else if (ff == 4) { serdata[0] =  0b00010000; serdata[1] = 0b00010000; }
 else if (ff == 5) { serdata[0] =  0b00100000; serdata[1] = 0b00100000; } 
 else if (ff == 6) { serdata[0] =  0b01000000; serdata[1] = 0b01000000; }
 else if (ff == 7) { serdata[0] =  0b11111111; serdata[1] = 0b11111111; }

   shregs.update(serdata);
}


