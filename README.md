# ECE 528 Homework 3
## Section I: Review Questions

1. **The MSP432 uses the eUSCI_A modules for UART communication. Describe the function of the following registers:**
   - UCAxBRW (Baud Rate Control Word)
   - UCAxMCTLW (Modulation Control Word)
   - UCAxCTLW0 (Control Word 0)
   - UCAxRXBUF (Receive Buffer)
   - UCAxTXBUF (Transmit Buffer)
       
   The UCAxBRW register is used to set the baud rate. The UCAxMCTLW register is used to configure the baud rate modulation. The UCAxCTLW0 register can be used to select parity, direction of the shift register, and to select a clock source. The UCAxRXBUF and UCATXBUF registers are used to handle the incoming and outgoing bytes in UART communication. 
   
2. **What is the purpose of the UCAxSTATW status register in the UART module? Which bits indicate the following?**
   - Whether the UART module is currently transmitting
   - Whether a framing, parity, or overrun error has occurred
   - Whether the RX buffer contains unread data
     
     The UCAxSTATW register is used to read the status of the UART module. Bit 0 indicates whether the UART module is currently transmitting, bits 6 to 4 indicate framing, parity, or overrun errors, and bit 3 shows whether the RX buffer contains unread data.
     
3. **(a) Assume that the eUSCI_A3 module is using SMCLK as its clock source, which has a frequency of 12 MHz. Calculate the value that is needed to be written to the UCAxBRW register to configure the eUSCI_A3 module for 115200 baud.**  
   N = 12 MHz / 115200 = 104.167  
   
5. **Write a function named UART2_Init that configures the eUSCI_A2 module for the following settings:**
   - Baud Rate: 115200
   - Data Length: 8 bits
   - Parity: None
   - Stop Bits: 1
   - Bit Order Most Significant Bit (MSB) First
   - Clock Source: SMCLK (12 MHz)
   - Pins: P3.2 (UCA2TXD) and P3.3 (UCA2RXD)

   **(b) Suppose that you have a main program that is transmitting data using the eUSCI_A2 module given the configuration in part (a). Draw the waveform for the UART
   TX data line if the main program is transmitting two bytes: 0xF1 followed by 0x55. Clearly label the start bits, data bits, and stop bits. Assume that there is a
   50 ms delay between the two bytes.**  
   gfgdfgd
6. **What is the function of the eUSCI_B module? How does SPI communication differ from UART communication in terms of:**
   - Synchronization
   - Clocking
   - Signaling
   - Data Framing
7. **(a) Explain the role of the following SPI signals:**
   - SCLK
   - CS
   - MISO
   - MOSI
   
   **(b) What happens if multiple SPI peripheral devices have their CS line asserted
simultaneously on the MSP432?**  

8. **(a) Briefly describe the function of the UCBxCTLW0 (Control Word 0) register from the eUSCI_B module.**  
   **(b) Which bits need to be cleared or set in the UCBxCTLW0 register to configure the SPI mode used by the eUSCI_B module? Provide a description of each bit.**  
   **(c) Which field in the UCBxCTLW0 register selects the clock source used by the eUSCI_B module? Provide the values used and the corresponding clock sources.**  
10. **(a) Write a function named EUSCI_B0_SPI_Init that configures the eUSCI_B0 module for SPI communication with the following settings:**
    - SPI Mode: 0
    - Data Length: 8 bits
    - Bit Order: Most Significant Bit (MSB) First
    - Clock Source: SMCLK (12 MHz)
    - SPI Clock Frequency: 1 MHz
    - SPI format: 3-wire SPI
    - SPI Pins:
      - P1.5: SCLK (UCB0CLK)
      - P1.6: MOSI (UCB0SIMO)
      - P1.7: MISO (UCB0SOMI)
      - P9.0: Active Low Chip Select (GPIO)
      
    **(b) If a main program transmits one byte with a value of 0x57, draw the waveforms for:**
    - Chip Select (Active Low)
    - SCLK
    - MOSI  
      fgdfgd
