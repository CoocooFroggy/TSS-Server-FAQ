[Instructions (click me)](/TSwapS-FAQ/instructions)

**FAQ**

# Tadpole Swap Server

---

## Do I actually need to update in order to save blobs?

**No.** TSwapS does not return a valid blob to your device, meaning the phone will refuse to update so long as TSS is redirected to our TSwapS. 

## Is this anything new?

Yes, actually—I've not seen anyone redirect TSS for the purpose of *saving* blobs. And as far as I'm aware, this is the only known way to:
- Get ECID on unjailbroken A11 and lower devices without a computer 
- Get a valid AP Nonce on unjailbroken A12 and later devices without a computer

Even better, using APIs of popular blob saving websites such as SHSH Host and TSS Saver, it's possible to immediately save valid blobs for all signed firmwares without needing to input any information manually. However, these blobs would lack a generator, so I've elected not to implement this.

## Why and when would I use this?

If you haven't saved blobs before:  
If you're not jailbroken and don't have access to a computer, you can use TSwapS to start saving blobs for your device.

If you are jailbroken or are already saving blobs somewhere else:  
You don't really have use for this, but you can redirect gs.apple.com on your home WiFi, so that any friends who try to install an update on your WiFi can start saving blobs instead lol.

## Why can't I see my current generator?

The boot-nonce in the phone's NVRAM is not a necessary piece of information in the SHSH Protocol. There is current only one known way to get this value while unjailbroken, requiring a computer. This value is only used to set your generator back if you reset it. This is caused by requesting AP Nonce in booted mode (running an OTA update again, choosing to save unjailbroken blobs with blobsaver), or updating/restoring the device. 

### Doesn't this make the blob useless?

**It doesn't make your blobs useless or invalid!** Your boot-nonce is still set in NVRAM, so you can reboot your device and your AP Nonce will remain the same, meaning you can still use the blobs.

When you go to use FutureRestore, simply fetch your generator, so that you can reuse the blobs saved without generator later, and then start the restore. Again, the generator is **not needed when saving blobs**. You will only use the generator if you're jailbroken and want to reuse a blob after the your nonce changed.

Whenever you have access a computer, you can read the generator and note it down. You can do this with libimobiledevice (simply run `ideviceinfo -k BootNonce`, then convert the base64 to hexadecimal), or with blobsaver. (Make _sure_ to press "Jailbroken" to keep your current AP Nonce, even if you're not jailbroken—don't let the wording fool you!) 

### In what circumstances does this persistent boot-nonce change?

After you use TSwapS, if you reboot and then request AP Nonce in booted mode (TSwapS again/use blobsaver 3.0+), or if you restore your device, your nonce will randomize. This will make all your blobs useless unless you noted down the generator *and* have a jailbreak to set the generator again.

## What is the Chip ID?

The Chip ID is an identifier that corresponds to your device's Application Processor. Visit [this page](https://www.theiphonewiki.com/wiki/CHIP) on The iPhone Wiki to match your Chip ID with your processor.

## What is the Board ID?

The Board ID is an identifier that corresponds to your device's hardware model. Visit [this page](https://www.theiphonewiki.com/wiki/BORD) on The iPhone Wiki to match your Board ID with your Board Config. Or simply look at the "Board Config" field in the Device Info page after performing TSwapS.

## What information is kept on the server?

No persistent information is kept.

## Why is this done through a server? Can this instead be done locally/offline?

The answer is definitely yes! You can already do this with some proxy apps like [Proxyman](https://apps.apple.com/us/app/proxyman-web-debugging-proxy/id1551292695), just not conveniently. I'd make an app, but unfortunately, I would rather not publish an app onto TestFlight with my real name. Unless someone else is willing to publish the app, you'll have to stick with the online method.
