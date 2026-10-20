# Numato Elbert V2 Configuration Tool



A Python utility for programming the SPI flash on the Numato Lab Elbert V2 FPGA development board.



## Requirements



- Numato Elbert V2 FPGA development board

- Linux system with access to the board's serial device

- Python 2.6-compatible environment for the modified script

- PySerial 2.7



# Installation



Install PySerial 2.7 in the Python environment used to run the script.



Verify that the serial module is available:



&#x20;   python -c "import serial; print serial.VERSION"



## Usage



1. Connect the Elbert V2 board to the computer.

2. Identify its serial device. On Linux, it may appear as `/dev/ttyACM0`.

3. Build your FPGA design in Xilinx ISE and locate the generated bitstream.

4. Run the configuration utility with the serial device and bitstream paths:



&#x20;      sudo python elbertconfig.py /dev/ttyACM0 /path/to/bitstream.bin



Replace `/dev/ttyACM0` and `/path/to/bitstream.bin` with the appropriate paths for your system.



## Compatibility



The script has been modified for compatibility with the legacy Python environment used by Xilinx ISE 14.7 on Red Hat Enterprise Linux 6.4.



Compatibility changes include handling byte-string indexing in Python 2, flushing progress output explicitly, and correcting the response-reading method call.



## Verification



The modified script has been tested with a Numato Elbert V2 board. The configuration utility detected the Micron M25P16 SPI flash, programmed the FPGA bitstream, and successfully ran an LED blink design on the hardware.



## Notes



- Programming the SPI flash changes the configuration stored on the board.

- Confirm that the bitstream is built for the correct FPGA and board.

- Preserve the original script's copyright and license notices.

- Check the original script's license terms before redistributing modified versions.
