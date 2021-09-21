FAQ

# Do I actually need to update in order to save blobs?

**No.** The server does not return a valid blob to your device, meaning the phone will refuse to update so long as TSS is redirected to the server. 

# What is the Chip ID?

The Chip ID is an identifier that corresponds to your device's Application Processor. Visit [this page](https://www.theiphonewiki.com/wiki/CHIP) on The iPhone Wiki to match your Chip ID with your processor.

# What is the Board ID?

The Board ID is an identifier that corresponds to your device's hardware model. Visit [this page](https://www.theiphonewiki.com/wiki/BORD) on The iPhone Wiki to match your Board ID with your Board Config.

# Why can't I see my current generator?

The boot-nonce in the phone's NVRAM is not a necessary piece of information in the SHSH Protocol. There is current only one known way to get this value while unjailbroken, requiring a computer. This value is only used to set your generator back if you reset it. This can be caused by running an OTA update again, reading the AP Nonce in booted state (for example, choosing to save unjailbroken blobs with blobsaver), or updating/restoring the device. 

Whenever you have access a computer, feel free to read the generator and note it down. You can do this with libimobiledevice (simply run `ideviceinfo -k BootNonce`, then convert the base64 to hexadecimal), or with blobsaver. (Make _sure_ to press "Jailbroken" to keep your current AP Nonce, even if you're not jailbroken—don't let the wording fool you!) 

# What information is kept on the server?

No persistent information is kept.
