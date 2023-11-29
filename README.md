# USB_MSC_U5

I have some problems running USB MSC device type on a STM32U5 using AZURE.

I posted here my full project and some info about the problem. The project started from a CUBEMX project, then I edited some files to complete it. 

In the "source" folder there are some of this **important** files.

After the program is running on my board, I see this new device on the **Device Manager** of my PC:

![Device Manager](/images/device.png)


But there are no hard drives present in Explorer.


If I put in pause the program, randomly, I see that it is always inside this function: **_ux_device_stack_transfer_request**

![Device Manager](/images/pause.png)

