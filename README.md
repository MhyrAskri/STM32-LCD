# STM32 LCD
## How to use:
In the first step, in the lcd.h file, in the includes section, change line 12 to the name of your micro.
For example, if you use STM32F4 micro series, write stm32f4xx_hal.h instead of stm32f1xx_hal.h.
Then include lcd.h in your project and run lcd through the following codes.
<code C>
  Lcd_PortType ports[] = { GPIOA, GPIOA, GPIOA, GPIOA };
	Lcd_PinType pins[] = {GPIO_PIN_4, GPIO_PIN_5, GPIO_PIN_6, GPIO_PIN_7};
	
	Lcd_HandleTypeDef lcd;
  lcd = Lcd_create(ports, pins, GPIOA, GPIO_PIN_1, GPIOA, GPIO_PIN_2, LCD_4_BIT_MODE);
</code C>
