# Part 2 - 7Segment Displays, Buttons and LEDs
This part covers the assembly of the 7Segment Display, the Buttons and the LED

## Parts needed
- 16x [LED yellow](https://de.aliexpress.com/item/32757762886.html?spm=a2g0o.order_list.order_list_main.17.1f1c5c5fcqS67x&gatewayAdapt=glo2deu)
- 7x [LED green](https://de.aliexpress.com/item/32757762886.html?spm=a2g0o.order_list.order_list_main.17.1f1c5c5fcqS67x&gatewayAdapt=glo2deu)
- 16 [8x8 Non-Self-Locking Button](https://de.aliexpress.com/item/4001159367703.html?spm=a2g0o.cart.0.0.5fbb4ae4lgbDyt&mp=1&gatewayAdapt=glo2deu)
- 2x [10uF elektrolyt capacitor](https://de.aliexpress.com/item/32951751425.html?spm=a2g0o.order_list.order_list_main.5.1f1c5c5fcqS67x&gatewayAdapt=glo2deu)
- 2x [100nF cermaic capacitor](https://de.aliexpress.com/item/1005001356274653.html?spm=a2g0o.order_list.order_list_main.11.1f1c5c5fcqS67x&gatewayAdapt=glo2deu)
- 4x [7 segment 3 Bit 0.36 common cathode](https://de.aliexpress.com/item/1005005667523190.html?spm=a2g0o.order_list.order_list_main.46.1f1c5c5fcqS67x&gatewayAdapt=glo2deu)
- 2x [7 segment 2 Bit 0.36 common cathode](https://de.aliexpress.com/item/1005005667523190.html?spm=a2g0o.order_list.order_list_main.46.1f1c5c5fcqS67x&gatewayAdapt=glo2deu)
- 2x [Max 7219](https://de.aliexpress.com/item/1005004266394173.html?spm=a2g0o.order_list.order_list_main.59.1f1c5c5fcqS67x&gatewayAdapt=glo2deu)
- 2x [DIP24](https://de.aliexpress.com/item/1005005432295225.html?spm=a2g0o.order_list.order_list_main.65.1f1c5c5fcqS67x&gatewayAdapt=glo2deu)
- Some [PCD Boards](https://de.aliexpress.com/item/1005004818919331.html?spm=a2g0o.store_pc_topSellerIng.8148356.3.45d21626uiU4HC&spm=a2g0o.store_pc_home.hotSpots_2004250068647.1&gatewayAdapt=glo2deu)

## Preview
[Finished assembly](./Images/)

## Electronic Shematic
TODO

# 3D Printing
## Front
Print the front with 50% infill

## Buttons
All Buttons can be printed with 10% infill.

## Electrical assembly
Take a look to the [Datasheets](./Datasheets/) and doublecheck if you have the same 7Segment Display as the datasheet is. Otherwise get the correct datasheet. 

Wiring is easy but takes a lot of time.
One Max7219 can handle 8Digits. You have 16 Digits, so you need 2 Max7219. 

I have connected Speed, Heading and the first 2 digits of the Alt display to the first 7219. The remaining 3 digits of the Alt display and all digits of the VS display are connected to the second 7219.

The segments of the displays that belong on a Max7219 must all be connected together. The segment connections are each connected individually to the 7219. See the data sheets. Additionally the 7219 needs 5V at the V+ input. In parallel to the power supply 2 capacitors must be connected in parallel. A 10uF electrolytic capacitor and a 100nF cermaic capacitor. The other side of the capacitor belongs to GND. Furthermore the 7219 needs at the ISET input a 41k Ohm resistor with a 5V power supply.

Wiring the rest is pretty simple. Each button needs GND and is connected to the Arduino at the switch wire. Each LED needs a series resistor. I recommend to try each light color with different resistors to get the desired brightness. Please note that 20mA per output should not be exceeded.

Pin Arduino | Description 
38	        | AP1 Btn  
39	        | Ap1 LED  
40	        | AP2 Btn  
41	        | AP2 LED  
42	        | LOC BTN  
43	        | LOC LED  
44	        | ATHR BTN  
45	        | ATHR LED  
46	        | EXPED BTN  
47	        | EXPED LED  
48	        | 1000 Btn  
49	        | 1000 LED  
50	        | APP BTN  
51	        | APP LED  
52	        | SPD Mach Btn  
53	        | HDG TRK Btn  
2	        | MET ALT Btn  
3	        | SPD LED  
4	        | MACH LED  
5	        | HDG LED  
6	        | TRK LED  
7	        | VS LED  
8	        | FPA LED  
9	        | SPD Managed LED  
10	        | HDG Managed LED  
11	        | Alt Managed LED  

## Assembly
In the 3D files directory there are different Pins to glue the components together. 