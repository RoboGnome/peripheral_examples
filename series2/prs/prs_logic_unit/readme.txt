prs_logic_unit

This project demonstrates the built-in PRS logic functions between channels.
Onboard push-buttons (PB0 and PB1) are set as PRS source. Onboard LED (LED1)
is set as PRS output.

Output uses the following truth table for OR logic function:
PB1   PB0   |  OUTPUT 
------------------------
1     1     |     1     
1     0     |     1    
0     1     |     1     
0     0     |     0  

When the push button (PB0 or PB1) is pressed, a logical low is sampled by the
GPIO and sent to the corresponding PRS channel

When the push button (PB0 or PB1) is released, a logical high is sampled by the
GPIO and sent to the corresponding PRS channel

A logical low output will have the LED off and a logical high output will have
the LED on.

Note: For EFR32xG21 radio devices, library function calls to CMU_ClockEnable() 
have no effect as oscillators are automatically turned on/off based on demand 
from the peripherals; CMU_ClockEnable() is a dummy function for EFR32xG21 for 
library consistency/compatibility.

===============================================================================

How To Test:
1. Update the kit's firmware from the Simplicity Launcher (if necessary)
2. Build the project and download to the Starter Kit
3. Press the Push Buttons and notice how the LED1 responds.

Note: Various other logic functions like AND, NAND, NOR, XOR, NOT etc are 
available. You can switch between these logic functions by changing the 
parameters passed when calling PRS_Combine() function in main.c.

Note: For EFR32xG22/xG23 devices, you may choose any asynchronous PRS channel as
your input B. For EFR32xG21/xG24 devices, you have to choose (input A - 1) as your
input B. This is reflected on the PRS channel selection in the source file

===============================================================================

Peripherals Used:
CMU    - FSRCO @ 20 MHz

Board:  Silicon Labs EFR32xG21 Radio Board (BRD4181A) + 
        Wireless Starter Kit Mainboard
Device: EFR32MG21A010F1024IM32
PRS   - Channel 0, PB0
        Channel 1, PB1 routed to LED1 (Output)
PD02  - push button PB0
PD03  - push button PB1
PB01  - PRS Channel 1

Board:  Silicon Labs EFR32xG22 Radio Board (BRD4182A) + 
        Wireless Starter Kit Mainboard
Device: EFR32MG22C224F512IM40
PRS   - Channel 1, PB0
        Channel 6, PB1 routed to LED1 (Output)
PB00  - push button PB0
PB01  - push button PB1
PD03  - PRS Channel 6

Board:  Silicon Labs EFR32xG23 Radio Board (BRD4263B) + 
        Wireless Starter Kit Mainboard
Device: EFR32FG23A010F512GM48
PRS   - Channel 1, PB0
        Channel 6, PB1 routed to LED1 (Output)
PB01  - push button PB0
PB03  - push button PB1
PD03  - PRS Channel 6

Board:  Silicon Labs EFR32xG24 Radio Board (BRD4186C) + 
        Wireless Starter Kit Mainboard
Device: EFR32MG24B210F1536IM48
PRS   - Channel 0, PB0
        Channel 1, PB1 routed to LED1 (Output)
PB01  - push button PB0
PB03  - push button PB1
PB04  - PRS Channel 1