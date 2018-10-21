# PhantomLights

Arduino project to run the LEDs for our halloween Phantom.

Hardware
Arduino Nano
3 x 8mm UV LEDs
4 x 5mm RGB LEDs
1 x 18 ohm resistor - for 3 UV LEDs in series
1 x 120 ohm resistor - for red leg of RGB LEDs
2 x 82 ohm resistor - for green and blue legs of RGB LEDs
12V 2A power supply

LED Locations
3 UV LEDs in head wired in series
Hands (RGB LEDs) are wired in parallel [2 RGB] -- [2 RGB] 
  2 RGB LEDs in right hand wired in series 
  2 RGB LEDs in left hand wired in series

Basic Wiring Info

12V input +
  --> multi-tap PCB-1
    • Arduino Nano Vin
    • CAT5-a Blue pair --> multi-tap PCB-2 Vin

12V Ground
  --> multi-tap PCB-1
    • Arduino Nano Gnd-1
    • CAT5-a Orange pair --> multi-tap PCB-2 GND
    
Head/UV LEDs
  multi-tap PCB-2 Vin --> 18 ohm resistor --> LED1 > LED2 > LED3 --> multi-tap PCB-2 GND
  
Right Hand
  multi-tap PCB-2 Vin --> CAT5-b Blue pair --> LED1 Anode > LED2 Anode
  CAT5-c Green --> 82 resistor --> LED1 Green RGB Cathode (-) Leg > LED2 Green RGB Cathode (-) Leg
  CAT5-c Green/White --> 82 resistor --> LED1 Blue RGB Cathode (-) Leg > LED2 Blue RGB Cathode (-) Leg
  CAT5-c Brown --> 120 resistor --> LED1 Red RGB Cathode (-) Leg > LED2 Red RGB Cathode (-) Leg
  
Left Hand
  multi-tap PCB-2 Vin --> CAT5-b Blue pair --> LED1 Anode > LED2 Anode
  CAT5-d Green --> 82 resistor --> LED1 Green RGB Cathode (-) Leg > LED2 Green RGB Cathode (-) Leg
  CAT5-d Green/White --> 82 resistor --> LED1 Blue RGB Cathode (-) Leg > LED2 Blue RGB Cathode (-) Leg
  CAT5-d Brown --> 120 resistor --> LED1 Red RGB Cathode (-) Leg > LED2 Red RGB Cathode (-) Leg
  
Phantom CAT5 wire connections
  splice/connect all wire pairs
    CAT5-d --> CAT5-a <-- CAT5-c
    CAT5-a is main trunk between control box and phantom
    CAT5-d/c are for hands
    CAT5-b is for UV LEDs

CAT5 Color Guide
  Blue Pair - 12V+
  Orange Pair - GND
  Green - Green RGB Cathode (-) Leg
  Green/White - Blue RGB Cathode (-) Leg
  Brown - Red RGB Cathode (-) Leg
  Brown/White - Unused
  
Arduino Pins
  redPin = 11 --> CAT5-a Brown
  greenPin = 10 --> CAT5-a Green
  bluePin = 9 --> CAT5-a Green/White

  
