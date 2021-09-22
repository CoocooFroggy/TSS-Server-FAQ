**Instructions**

[FAQ](/TSS-Server-FAQ/faq)

# Setup

1. Ensure you have an OTA Software Update available in **Settings > General > Software Update**. It can be any update, including a beta.
    1. You may need to remove any OTA blocking profiles, such as a tvOS profile.
    2. Ensure auto updates are disabled, so it doesn't update when you're not looking.
2. Download ["DNSCloak" from the App Store](https://apps.apple.com/us/app/dnscloak-secure-dns-client/id1452162351)
3. Download <a href="/TSS-Server-FAQ/cloak.txt" download="Redirect.txt">this text file</a> and save it somewhere accessible to the native Files app.
4. Open DNSCloak and press the hamburger menu icon in the top left corner.
5. Under General options, enable "Connect on Demand" to ensure that the VPN does not disconnect. 
6. Expand "Advanced options" at the very bottom, and scroll down to "Enable Cloaking" (umbrella icon)
7. Toggle the switch on, and select the `Redirect.txt` file you downloaded in step 3.
8. Press the back arrow at the top left
9. Search for "cloudflare" in the search bar at the top. Tap on it and press "Use this server."
10. Follow the steps to setup the VPN configuration.
    1. If the app seems to be stuck starting DNS server, dismiss the app (without closing it completely!) and re-enter. If you see a square ■ on the toolbar at the top, you're connected. Otherwise, press the play button ▶ on the toolbar.

# Execution

Open Safari and go to [gs.apple.com](http://gs.apple.com)

You should see a website indicating that the redirection succeeded. Follow the steps on the website (which are as follows):

1. Head to Settings > General > Software Update
2. Attempt to install any update
3. Wait for "Verifying Update" to fail
    1. If it doesn't fail, and your screen goes black, your phone was able to communicate with Apple's servers somehow. Hard reboot your phone immediately to cancel the update. Ensure that gs.apple.com is really redirecting before trying again.
4. Return to [gs.apple.com](http://gs.apple.com) and refresh the page. All the details for your device will appear.

# Completion

1. Delete the update file in **Settings > General > iPhone Storage > iOS XX.X > Delete Update**
2. Feel free to install reinstall your OTA blocker profiles, or remove the beta if you needed it.
3. Delete the DNSCloak application. This will remove the VPN configuration and won't redirect gs.apple.com anymore.
4. Automatically save blobs on device with [a shortcut](https://routinehub.co/shortcut/9846/)
