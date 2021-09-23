**Description**

[Instructions](/TSwapS-FAQ/instructions)

[FAQ](/TSwapS-FAQ/faq)

# Tadpole Swap Server

---

## What does TSwapS do?

**First of all, what is supposed to happen?**

When your device wants to perform an over-the-air (OTA) update, right before install, a few things happen:

- Your device sets a random boot-nonce (NVRAM generator) and derives its AP Nonce
- Your device makes a request to Apple's TSS with that AP Nonce, device information, ECID (and firmware digests + unique build ID)
- Apple's TSS responds with a signature "blob" for that version, and the device begins the restore process

**So how does TSwapS change things?**

- Your device sets a random boot-nonce (NVRAM generator) and derives its AP Nonce
- Your device makes a request to *TSwapS* with that AP Nonce, device information, ECID (and firmware digests + unique build ID)
- *TSwapS responds with an error, so the device does not update*
- *You can visit TSwapS and see the information that your device sent (AP Nonce, ECID, Board ID and Chip ID), and TSwapS also parses the Board ID and Chip ID to find your device's identifier and board config.*

[Visit the FAQ](/TSwapS-FAQ/faq) for more information on how this changes blob saving, and why we don't need to know the generator.

[Visit the Instructions](/TSwapS-FAQ/instructions) page to use TSwapS.
