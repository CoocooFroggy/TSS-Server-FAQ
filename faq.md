[Instructions](/TSS-Server-FAQ/instructions)

**FAQ**

# Do I actually need to update in order to save blobs?

**No.** The server does not return a valid blob to your device, meaning the phone will refuse to update so long as TSS is redirected to the server. 

# Is this anything new?

Yes, actually—I've not seen anyone redirect TSS for the purpose of *saving* blobs. And as far as I'm aware, this is the only known way to:
- Get ECID on unjailbroken A11 and lower devices without a computer 
- Get a valid AP Nonce on A12 and later devices without a computer

Even better, using APIs of popular blob saving websites such as SHSH Host and TSS Saver, it's possible to immediately save valid blobs for allcsigned firmwares without needing to input any information manually. However, these blobs would lack a generator, so I've elected not to implement this.

# What is the Chip ID?

The Chip ID is an identifier that corresponds to your device's Application Processor. Visit [this page](https://www.theiphonewiki.com/wiki/CHIP) on The iPhone Wiki to match your Chip ID with your processor.

# What is the Board ID?

The Board ID is an identifier that corresponds to your device's hardware model. Visit [this page](https://www.theiphonewiki.com/wiki/BORD) on The iPhone Wiki to match your Board ID with your Board Config.

# Why can't I see my current generator?

The boot-nonce in the phone's NVRAM is not a necessary piece of information in the SHSH Protocol. There is current only one known way to get this value while unjailbroken, requiring a computer. This value is only used to set your generator back if you reset it. This can be caused by running an OTA update again, reading the AP Nonce in booted state (for example, choosing to save unjailbroken blobs with blobsaver), or updating/restoring the device. 

Whenever you have access a computer, feel free to read the generator and note it down. You can do this with libimobiledevice (simply run `ideviceinfo -k BootNonce`, then convert the base64 to hexadecimal), or with blobsaver. (Make _sure_ to press "Jailbroken" to keep your current AP Nonce, even if you're not jailbroken—don't let the wording fool you!) 

# What information is kept on the server?

No persistent information is kept.

# Why is this done through a server? Can this instead be done locally/offline?

The answer is most likely yes! Unfortunately, I would rather not publish an app onto TestFlight with my real name. Unless someone else would be willing to publish the app, you'll have to stick with the online method.
