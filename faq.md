
# What is the Board ID?

The Board ID is an identifier that corresponds to your device's hardware model. Visit [this page](https://www.theiphonewiki.com/wiki/BORD) on The iPhone Wiki to match your Board ID with your Board Config.

# What is the Chip ID?

The Chip ID is an identifier that corresponds to your device's Application Processor. Visit [this page](https://www.theiphonewiki.com/wiki/CHIP) on The iPhone Wiki to match your Chip ID with your processor.

# Why can't I see my current generator?

The boot-nonce in the phone's NVRAM is not a necessary piece of information in the SHSH Protocol. There is current only one known way to get this value while unjailbroken, requiring a computer. This value is only used to set your generator back if you accidentally reset it. This can be caused by running an OTA update again, or reading the AP Nonce in booted state (for example, choosing to save unjailbroken blobs with blobsaver 3.0+). 
