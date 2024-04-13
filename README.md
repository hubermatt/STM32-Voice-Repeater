This is a simple voice repeater project. 

The user presses a "record" button, says something, then presses the "repeat" button. The project 
utilizes several capabilities of the STM32 Nucleo L476RG development board, which are: Timers, 
ADC, DAC, I/O, interrupts, and DMA. The main.h file should be run with the HAL drivers that
are available to use in the STM32Cube IDE.

Below is the purpose of each part of this project:
Timer: Triggers the capture of data (the speaker input) at the specified time.
ADC: Converts each data capture into an 8-bit binary number and stores all of them in an array.
DAC: Unloads the array of binary numbers, converts them back to analog signal, then buffers the signal.
Interrupts: Jumps to the correct lines of code whenever one of the "record" or "repeat" buttons is pushed.
DMA: Stores each of the captured data points in the RAM of the microcontroller instead of bogging down the
  CPU. Helps the program to run quicker, putting the data together in the RAM to be easily unloaded to the speaker.
