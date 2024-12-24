UART (Universal Asynchronous Receiver Transmitter) Protocol

About UART Protocol

1. UART is a hardware communication protocol that uses asynchronous serial communication and is widely used for serial communication between devices.

2. It is used to transmit and receive serial data between devices using two wires: one for transmitting (Tx) and one for receiving (Rx).

3. UART transmit data asynchronously, which means there is no clock signal to synchronize the output of bits from the transmitting.

How its works

1. Data Transmission- UART transmit data one bit at a time. It uses a start bit to signal a beginning of a data packet and a stop bit to signal the end. This allow the receiving UART to known when to start and stop reading the bits.

2. Baud Rate- The speed of data transfer is measured in bit per second (bps) and is known as the baud rate. Both transmitting and receiving UART must operate at same baud rate.

3. Asynchronous Communication- unlike synchronous  communication protocol, UART does not use clock signal to synchronize data transmission. Instead, it relies on the start and stop bits to manage timing.

Working of UART:

STEP 1: Data bus send data to the UART

1. The UART that is going to transmit data receives data from a data bus.
2. The data bus is used to send data to the UART by another device like CPU, memory or microcontroller.
3. Data is transferred from the data bus to the transmitting UART in parallel form.

STEP 2: UART creates data packets

1. After the transmitting UART gets the parallel data from the data bus.
2. Then, UART creating the data packet by adding start bit, a parity bit and a stop bit.
3. Each packet contain 1 start bit, 5 to 9 data bits (depending on the UART),an optional parity bit, and 1 or 2 stop bits.

Data Packet Formation:

Start bit: 
To start transmission of data transmission line goes high to low for clock cycle(set 0 bit).
Receiver read this bit starts reading data in data frame.

Data Frame: 
The data frame contain the actual data being transferred.
It can be 5 bit up to 8 bit long.

Parity Bit:
Using Parity bit we can identify whether we have received data correctly or not.
The parity bit is way for the receiving UART to tell if any data has changed during transmission.
Bits can changed by electromagnetic radiation, mismatched baud rates or long distance data transfers.
If the parity bit is a 0(even parity), total number of 1 bit in data frame.
If the parity bit is a 1(odd parity), total number of 1 bit in data frame.
UART receiver checks parity bit.
When the parity bit matches the data, the UART knows that the transmission was free of errors.
If not match, then data was changed.

Stop Bit:
To signal the end of the data packet, the sending UART drive the data transmission line from a low voltage to a high voltage level(set 1 bit).

STEP 3: UART Transmitter send data to UART Receiver

1. UART 1 Transmitter(Tx pin) send this packet serially to UART 2 Receiver(Rx pin).
2. The receiving UART reads the data packet bit by bit at its Rx pin.

STEP 4: UART Receiver received data & send it parallel.

1. The receiving UART then convert the data back into parallel form and removes the start bit, parity bit and stop bits.
2. Finally, the UART Receiver transfers data packet parallel to the data bus on the receiving end.

Component of UART

Clock Generator: Generates the timing signals.
Shift Register: Convert data b/w serial and parallel forms.
Control logic: Manages the data flow and ensure proper timing.

Mode of operation

Simplex: Data flow in one direction only.
Half Duplex: Data can flow in both direction, but not simultaneously.
Full Duplex: Data can flow in both direction simultaneously.

Application

UART is widely used in microcontroller, GPS Modules, Bluetooth module and other embedded system for data transmission and control.

Advantages

1. Simplicity: Easy to implement and required only two wire for communication.
2. Cost Effective: Less expensive than parallel communication due to fewer wires.
3. Bus complexity is less.
4. Speed is configurable.
5. Error identification.

Limitation

1. Speed: Generally Slower than other  communication protocol like SPI and I2C.
2. Distance: Limited to short distance communication.
3. Start and stop bits required.
4. Asynchronous communication.
5. Redundant bit are present{start + stop + parity bit}.
