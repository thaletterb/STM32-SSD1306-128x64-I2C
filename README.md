# STM32-SSD1306-I2C Driver

Driver for a 128x64 OLED Display Module using the SSD1306 IC. 

# Preqrequisites
* [st-util] (github.com/texane/stlink.git)
* [STM32 Standard Periphereral library](http://www2.st.com/web/en/catalog/tools/FM147/CL1794/SC961/SS1743/LN1939)
* [GNU Toolchain](https://sourcery.mentor.com/sgpp/lite/arm/portal/subscription?@template=lite)

# Build Instructions
1. Update 'Makefile.common' and point LIBROOT and TOOLROOT to local directories where the standard library and GNU toolchain binaries are installed, respectively
2. Navigate into the source directory 'SSD1306'
3. Compile and link
``` $ make

# Flashing Instructions
1. Start st-util and force to use version 1
``` $ st-util -1

2. In a second terminal, navigate to the directory with the .elf binary and launch gdb
``` $ arm-none-eabi-gdb SSD1306.elf

3. Tell gdb which port to look for the discovery board on. `st-util -1` defaults to port 4242
``` (gdb) target extended-remote :4242

4. Load the binary
``` (gdb) load

5. Execute
``` (gdb) continue

# Credits
[Discovering the STM32 Microcontroller - Geoffrey Brown](http://www.cs.indiana.edu/~geobrown/book.pdf)
[STM32VLDISCOVERY Programming Tutorial - Radoslaw Kwiecien ](http://en.radzio.dxp.pl/stm32vldiscovery/)

