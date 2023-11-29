Inside the "usb_otg.c" file I added the line "__HAL_RCC_SYSCFG_CLK_ENABLE();" inside the function "MX_USB_OTG_HS_PCD_Init" to make things running, but not working.
