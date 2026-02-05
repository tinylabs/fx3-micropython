TODO:
- Pull dependencies using their dependency resolution .mtb/.mtbx
- Compile libraries for each chipset/cpu/package combination.
-   CM0+ should only need USB stack + USB drivers + DMA + IPC + SPI + SMIF.
-   CM4 will need all peripheral drivers (Unused will compile out with -ffunction-sections -fdata-sections)
- Port cypress USB stack to run only on the Cortex-M0
-   CM0 handles USB enumeration.
-   Virtual REPL CDC.
-   MSC for CM4 image update. FPGA bitstream update.
-   FPGA updates over SPI.
-   High speed USB <-> FIFO interface to FPGA
-   Instantiating bulk endpoints for CM4 usage.
-   Tickling DMA for USB transactions.
-   Interfacing to CM4 via IPC when data buffers are ready.
- CM4 will run micropython.
-   Communicate with CM0 for REPL.
-   Pass enumeration VID/PID descriptors to CM0.
-   Request endpoints from CM0.
-   Basic peripherals comms (UART/SPI/I2C).
-   Access to FPGA bus via high speed FIFO interface.
-   Access littlefs filesystem via CM0 IPC SMIF low level commands.
-   Run init python script from filesystem.

  
- Get enumeration bulk endpoints working
- Create virtual serial port managed by CM0 using IPC
- Port micropython over to CM4
- Use virtual serial port for REPL
- Use external 8MB SPI flash for file system storage
- Manage micropython heap using portion of 128kB RAM for locals
- Use memoryview for portion of onchip 1MB SRAM and some micropython heap
- Put frozen .mpy modules on 512kB onchip flash
- Implement high speed FPGA access via FIFO interface/bulk USB EP
- Implement mass storage device on CM0 to exposed micropython filesystem.
-   Reset CM4/re-enumerate when ejected.
  
Later:
- Include ulab for cmsis-dsp access
