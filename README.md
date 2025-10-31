# PIC16F877A-7Segment-Counter
Dual 7-segment counter using PIC16F877A
Author: M. H. Afifi

This project is a two-digit 7-segment counter based on the PIC16F877A microcontroller, written in MikroC PRO for PIC. The goal was to create a simple but complete example that shows how to use timers, interrupts, and multiplexed displays in an embedded system.
The counter can work in two modes:

Manual Mode – The user controls the count using push buttons.

Auto Mode – The counter automatically increases at a steady rate using Timer0 interrupts.

Three push buttons are connected to PORTD:

1-UP (RD0) – Increments the counter.

2-DOWN (RD1) – Decrements the counter.

3-LOOP (RD2) – Switches between manual and auto mode.

4-The display is a common cathode dual 7-segment module. Both digits share the same segment lines, and the software rapidly switches between them (multiplexing). This makes it look like both digits are lit at the same time, even though only one is active at any given moment.

The code uses Timer0 interrupts to handle both display refresh and timing for the auto mode. This allows the main program to stay simple and focus on checking button inputs and updating the counter.
To ensure stable performance:

1-Volatile variables are used for all data shared between the main code and the interrupt routine.

2-Global interrupts are briefly disabled when updating shared values to prevent timing conflicts.

3-Button inputs are debounced in software to remove electrical noise from mechanical switches.

4-A small lookup table for the 7-segment patterns is stored in Flash memory (const) to save RAM.

This project is a good reference for learning how to:

1-Configure digital I/O and Timer0 on a PIC16F877A.

2-Use interrupts effectively without blocking the main loop.

3-Drive multiplexed 7-segment displays.

4-Handle buttons cleanly and switch between modes in embedded C.
