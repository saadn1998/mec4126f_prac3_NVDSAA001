# mec4126f_prac3_nvdsaa001
MEC4126F, prac 3

// Description----------------------------------------------------------------|
/*
 * Turns on the board LEDs
 */
// DEFINES AND INCLUDES-------------------------------------------------------|

#define STM32F051                                                  //COMPULSORY
#include <stdio.h>
#include "stm32f0xx.h"											   //COMPULSORY
#include "lcd_stm32f0.h"

// GLOBAL VARIABLES ----------------------------------------------------------|

struct age_data
{
	int date;
	int month;
	int year;
	int age;
};

// FUNCTION DECLARATIONS -----------------------------------------------------|

void main(void);                                                   //COMPULSORY

// MAIN FUNCTION -------------------------------------------------------------|

void main(void)
{
	init_LCD();
	struct age_data x1= {11, 12, 1998, 23};
	char buffer[80];
	

	while(1)
	{
		for(int x=0;x<=x1.age;x++)
			{

				sprintf(buffer,"%d",x);
				delay(100000);
				lcd_putstring(buffer);
				delay(100000);
				lcd_command(CLEAR);
			}

	}
}

// OTHER FUNCTIONS -----------------------------------------------------------|
