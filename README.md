TODO:
- Port cypress USB stack to run only on the Cortex-M0
- Get enumeration bulk endpoints working
- Create virtual serial port managed by CM0 using IPC
- Port micropython over to CM4
- Use virtual serial port for REPL
- Use external 8MB SPI flash for file system storage
- Manage micropython heap using portion of 128kB RAM for locals
- Use memoryview for portion of onchip 1MB SRAM and some micropython heap
- Put frozen .mpy modules on 512kB onchip flash
- Implement high speed FPGA access via FIFO interface/bulk USB EP

Later:
- Include ulab for cmsis-dsp access
