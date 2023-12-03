# USB_MSC_U5

I have some problems running USB MSC device type on a STM32U5 using AZURE.

I posted here my full project (*USB_MSC_newprj.zip*) and some info about the problem. The project started from a CUBEMX project, then I edited some files to complete it and for doing some personalization for my **board**. 

Electrically the connection to the **USB-C** connector is simple: just the two DP and DN wires, I did not use the UCPD functionality, and I did not connect the CC1/2 pins to GND using a 5.1Kohm resistor [as in this thread](https://community.st.com/t5/stm32-mcus-other-solutions/how-to-connect-the-cc-pin-when-make-usb-type-c-compatible-to/td-p/303605). 
I think it's not a problem because I'm connecting the board with a USB-C to USB-A cable on a PC port which is USB2.

In the "source" folder there are some of this **important** files.

After the program is running on my board, I see this new device on the **Device Manager** of my PC:

![Device Manager](/images/device.png)


But there are no hard drives visible in Explorer. I'm using a **exFAT** formatted SDCard of about 256GByte. The initialization of the SDCard completed well, and I have the IRQ for the DMA transfer fired without problems.


If I put in pause randomly the program, I see that it is always inside this function: **_ux_device_stack_transfer_request**

![Device Manager](/images/pause.png)



