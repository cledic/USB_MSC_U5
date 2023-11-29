1. **usb_otg.c** I added the line "__HAL_RCC_SYSCFG_CLK_ENABLE();" inside the function "MX_USB_OTG_HS_PCD_Init" to make things running, but not working.
2. **app_usbx_device.h** Where I configured the stack size
3. **ux_device_msc.c** Here I use the "HAL_SD_ReadBlocks_DMA" and "HAL_SD_BlockBlocks_DMA" function to access the SDCard.I used a flag mechanism to manage the termination of the transfer with the DMA.
