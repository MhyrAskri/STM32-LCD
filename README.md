## How to use
In the first step, in the lcd.h file, in the includes section, change line 12 to the name of your micro.
For example, if you use STM32F4 micro series, write stm32f4xx_hal.h instead of stm32f1xx_hal.h.
Then include lcd.h in your project and run lcd through the following codes.
```C
  Lcd_PortType ports[] = { GPIOA, GPIOA, GPIOA, GPIOA };
  Lcd_PinType pins[] = {GPIO_PIN_4, GPIO_PIN_5, GPIO_PIN_6, GPIO_PIN_7};	
  Lcd_HandleTypeDef lcd;
  lcd = Lcd_create(ports, pins, GPIOA, GPIO_PIN_1, GPIOA, GPIO_PIN_2, LCD_4_BIT_MODE);
```
>**Lcd_PortType ports[]** </br>
- We use this line of code to write the ports related to the LCD data pins, which are D4 to D7 from left to right.
>**Lcd_PinType pins[]** </br>
- We use this line of code to write the pins related to the LCD data pins, which are D4 to D7 from left to right.
>**Lcd_HandleTypeDef lcd;** </br>
- We use this line of code to create a variable of type Lcd_HandleTypeDef to use it where needed.
>**lcd = Lcd_create(ports, pins, RS_GPIO_Port, RS_Pin, EN_GPIO_Port, EN_Pin, LCD_4_BIT_MODE);** </br>
- We use this line of code to make a complete LCD according to its bases and assign it to the lcd variable.

> [!IMPORTANT]
> For complete information on how to use the library functions correctly in the project, read the comments inside the lcd.c file.

```C
/**
 * Initialize 16x2-lcd without cursor
 */
void Lcd_init(Lcd_HandleTypeDef * lcd);
```

```C
/**
 * Write a number on the current position
 */
void Lcd_int(Lcd_HandleTypeDef * lcd, int number);
```

```C
/**
 * Write a string on the current position
 */
void Lcd_string(Lcd_HandleTypeDef * lcd, char string[], size_t size);
```

```C
/**
 * Set the cursor position
 */
void Lcd_cursor(Lcd_HandleTypeDef * lcd, uint8_t row, uint8_t col);
```

```C
/**
 * Clear the screen
 */
void Lcd_clear(Lcd_HandleTypeDef * lcd);
```
