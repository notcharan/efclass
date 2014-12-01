/* Example 14.3 - Digital Out emulation using control registers and flashing LED */

void delay(void)

// Define addresses of digital IO control regs as pointers to volatile data

#define FIO0DIR0 (*(volatile unsigned char *) (0x2009C000))
#define FIO0PIN0 (*(volatile unsigned char *) (0x2009C014))
#define FIO2DIR0 (*(volatile unsigned char *) (0x2009C040))
#define FIO2PIN0 (*(volatile unsigned char *) (0x2009C054))
void delay(void);
char a, b, i;

int main() {

    FIO0DIR0 =0x00;
    FIO2DIR0 =0xFF;
    while (1)
    {
        if((FIO0PIN0 & 0x01) == 1)//if(input==1)
        { 
            a = 0x01;
            b = 0x02;
        }
        else{
            a = 0x02;
            b = 0x01;
        }
        FIO2PIN0 |=a;
        delay();
        FIO2PIN0 &=~a;
        delay();
        
       for(i = 0;i<=3;i++)
        {
            FIO2PIN0 |=b;
            delay();
            FIO2PIN0 &=~b;
            delay();
        }
    }
}

void delay (void)
{
    int j;
    for (j = 0; j<1000000;j++)
    {
        j++;
        j--;
     }
}