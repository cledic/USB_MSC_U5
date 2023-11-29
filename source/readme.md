1. **usb_otg.c** I added the line "__HAL_RCC_SYSCFG_CLK_ENABLE();" inside the function "MX_USB_OTG_HS_PCD_Init" to make things running, but not working.
2. **app_usbx_device.h** Where I configured the stack size
3. **ux_device_msc.c** Here I use the "HAL_SD_ReadBlocks_DMA" and "HAL_SD_BlockBlocks_DMA" function to access the SDCard.I used a flag mechanism to manage the termination of the transfer with the DMA.
4. **app_usbx_device.c** This is how I start the USB process:


`static VOID app_ux_device_thread_entry(ULONG thread_input)
{
  /* USER CODE BEGIN app_ux_device_thread_entry */
  TX_PARAMETER_NOT_USED(thread_input);

  MX_USB_OTG_HS_PCD_Init();

  HAL_PCDEx_SetRxFiFo(&hpcd_USB_OTG_HS, 0x100);
  HAL_PCDEx_SetTxFiFo(&hpcd_USB_OTG_HS, 0, 0x60);
  HAL_PCDEx_SetTxFiFo(&hpcd_USB_OTG_HS, 1, 0x60);
  HAL_PCDEx_SetTxFiFo(&hpcd_USB_OTG_HS, 2, 0x60);
  /* USER CODE END USB_Device_Init_PreTreatment_1 */

  /* initialize the device controller driver*/
  _ux_dcd_stm32_initialize((ULONG)USB_OTG_HS, (ULONG)&hpcd_USB_OTG_HS);

  /* Start device USB */
  HAL_PCD_Start(&hpcd_USB_OTG_HS);
}`
