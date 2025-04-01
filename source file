#include <msp430.h> // Include the MSP430 header file

#define LED_PIN BIT2 // Define P1.2 as LED_PIN

void delay_ms(unsigned int ms);

void main(void) {
    WDTCTL = WDTPW | WDTHOLD; // Stop the Watchdog Timer

    P1DIR |= BIT2;  // Set P1.2 as output
    P1OUT |= BIT2;  // Initialize P1.2 to HIGH (LED OFF in negative logic)

    while (1) {
        P1OUT &= ~BIT2; // Set P1.2 to LOW (LED ON)
        delay_ms(200);    // 200ms (2 seconds) delay
        P1OUT |= BIT2;  // Set P1.2 to HIGH (LED OFF)
        delay_ms(200);    // 200ms (2 seconds) delay
    }
}

// Function for delay in milliseconds
void delay_ms(unsigned int ms) {
    while (ms--) {
        __delay_cycles(300); // 1 ms delay assuming 1 MHz clock
    }
}
