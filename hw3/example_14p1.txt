/* Example 14.1 - Digital Out emulation using control registers and flashing LED */

void delay(void)

// Define addresses of digital IO control regs as pointers to volatile data

#define FIO2DIR0 (*(volatile unsigned char *) (0x2009C040))
#define FIO2PIN0 (*(volatile unsigned char *) (0x2009C054))
void delay(void);

int main() {
    FIO2DIR0 =0xFF;
    while (1)
    {
        FIO2PIN0 |=0x01;
        delay();
        FIO2PIN0 &=~0x01;
        delay();        
    }
}

// Delay Function

void delay (void)
{
    int j;
    for (j = 0; j<1000000;j++)
    {
        j++;
        j--;
     }
}