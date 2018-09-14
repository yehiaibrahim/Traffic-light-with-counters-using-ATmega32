# Traffic-light-with-counters-using-ATmega32
//* main.c







#include "types.h"
#include "DIO_interface.h"
#define F_CPU 12000000
#include <util/delay.h>
int main(void)
{
	// make pin A0 output

	uint8 seg_arr[10] = {0b10100000,0b11111001,0b11000100,0b11010000,0b10011001,0b10010010,0b10000010,
			0b11111000,0b10000000,0b10011000};
	uint8 arr[4]={0b10100000,0b11111001,0b11000100,0b11010000};
	uint8 i;
	uint8 z;
	uint8 x;


	DIO_voidSetPortDirection(0,1);
	DIO_voidSetPortDirection(1,1);
	DIO_voidSetPortDirection(2,1);
	while(1)
	{
		for(x=0;x<4;x++)
		{
			switch(x)

		{
		case 0:
		DIO_voidSetPortvalue(2,0b000000001);
		for (i=0;i<3;i++)
		{
			DIO_voidSetPortvalue(1,arr[i]);

					for (z=0;z<10;z++)
					{
						DIO_voidSetPortvalue(0,seg_arr[z]);

						_delay_ms(1000);

					}
		}
		break;
		case 1:
				DIO_voidSetPortvalue(2,0b00000010);
				for (i=0;i<2;i++)
				{
					DIO_voidSetPortvalue(1,arr[i]);

							for (z=0;z<5;z++)
							{
								DIO_voidSetPortvalue(0,seg_arr[z]);

								_delay_ms(1000);

							}
				}
				break;
		case 2:
						DIO_voidSetPortvalue(2,0b00000100);
						for (i=0;i<2;i++)
						{
							DIO_voidSetPortvalue(1,arr[i]);

									for (z=0;z<5;z++)
									{
										DIO_voidSetPortvalue(0,seg_arr[z]);

										_delay_ms(1000);

									}
						}
						break;
		case 3:
						DIO_voidSetPortvalue(2,0b00000010);
						for (i=0;i<2;i++)
						{
							DIO_voidSetPortvalue(1,arr[i]);

									for (z=0;z<5;z++)
									{
										DIO_voidSetPortvalue(0,seg_arr[z]);

										_delay_ms(1000);

									}
						}
}
		}
	}
	return 0;
}

 
