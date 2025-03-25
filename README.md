# USB-Audio-Player
Embedded audio project to interface USB audio data with an audio codec and send the output to a headphone jack.

This is my first STM32 project, where I'm learning about DAC, DMA, I2C, and I2S. It involves using an audio codec (CS43L22), which converts digital audio data into an analog signal that can be played through speakers or headphones connected to the board. 

# Definitions
Audio codec (coder-decoder) - a hardware component that encodes and decodes digital audio signals, an audio codec chip converts digital audio data (PCM, pulse code modulation) into an analog signal for playback on speakers or headphones, or the other way around
  
I2C - a serial communication protocol used for communication between microcontrollers and peripheral devices. In this project, it is used to communicate with the CS43L22 codec. I2C allows multiple controllers and devices to share the same bus and communicate using two lines:
  
  SDA (Serial Data): Data line for transferring information
  
  SCL (Serial Clock): Clock line to synchronize data transfer

I2S - Inter-IC Sound, a serial bus interface standard designed specifcially for trasnferring audio data between peripherals such as ADC, or in this case from th microcontroller to the CS43L22 DAC. 

How It Works
The USB Audio Device Library is used to configure the board to be recognized as a USB audio output device. This allows the STM32 board to receive audio data directly from a laptop or PC by USB, so it is detected by your PC as an external audio device when you plug it in. 

I2C is used to configure the CS43L22 audio codec, which is connected to the microcontroller through the I2C bus. The microcontroller sends commands (such as enabling/disabling channels, setting volume levels, etc) to the codec using I2C. I2S is used to send the audio data from the microcontroller to the codec once it has been configured. The codec converts the digital audio data into an analog signal that can be played through the connected headphones or speakers.

