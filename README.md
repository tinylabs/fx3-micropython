```
TODO:
- Pull dependencies using their dependency resolution .mtb/.mtbx
- Compile libraries for each chipset/cpu/package combination.
   CM0+ should only need USB stack + USB drivers + DMA + IPC + SMIF.
   CM4 will need all peripheral drivers + IPC (Unused will compile out with -ffunction-sections -fdata-sections)
- Port cypress USB stack to run only on the Cortex-M0
   CM0 handles USB enumeration.
   Virtual REPL CDC.
   MSC for CM4 image update (U2F).
   MTP access to micropython filesystem.
   High speed USB <-> FIFO interface to FPGA
   Instantiating bulk endpoints for CM4 usage.
   Tickling DMA for USB transactions.
   Interfacing to CM4 via IPC when data buffers are ready.
- CM4 will run micropython.
   Communicate with CM0 for REPL.
   Pass enumeration VID/PID descriptors to CM0.
   Request endpoints from CM0 (before enumeration).
   Basic peripherals comms (UART/SPI/I2C).
   FPGA updates over SPI (either from bitstream in filesystem or MSC upload over USB).
   Access to FPGA internal bus via high speed FIFO interface.
   Access littlefs filesystem via CM0 IPC SMIF low level commands.
   Run init python script from filesystem.

- Get enumeration bulk endpoints working
- Create virtual serial port managed by CM0 using IPC
- Port micropython over to CM4
- Use virtual serial port for REPL
- Move CM0 IRQs/hot paths to 128kB SRAM to decongest 512kB flash.
- Use external 8MB SPI flash for file system storage
- Manage micropython heap using portion of 128kB RAM for locals. Use 1MB SRAM for large object storage.
- Put frozen core .mpy modules on 512kB onchip flash
- Implement high speed FPGA access via FIFO interface/bulk USB EP
- Implement mass storage device on CM0 to exposed micropython filesystem.
-   Reset CM4/re-enumerate when ejected.

Later:
- Implement CDC-NCM and tie into micropython networking
- Include ulab for cmsis-dsp access
```
