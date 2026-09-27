# Setup

Device and system requirements follow Apple's article: [iPhone Mirroring: Use your iPhone from your Mac](https://support.apple.com/en-us/120421). The steps below are based on it and on real use.

## Devices and account

- Mac: Apple silicon or the Apple T2 Security Chip, macOS 15 or later.
- iPhone: iOS 18 or later, with a passcode set.
- Both signed in to the same Apple Account, with two-factor authentication on.
- Bluetooth and Wi-Fi on for both, and the devices near each other.
- The Mac isn't sharing its internet connection or using AirPlay or Sidecar.
- One Mac and one iPhone at a time. iPhone Mirroring isn't available in the EU.

## First connection

1. Open iPhone Mirroring on the Mac, from the Dock, the Applications folder or Spotlight.
2. If it asks you to unlock your iPhone, enter the passcode on the phone. The first connection after the phone restarts usually needs this too.
3. If it asks about iPhone notifications, choose what you prefer.
4. If it asks whether to require your Mac login to access the iPhone: "Ask every time" is safer; authenticating automatically means fewer interruptions while the AI works. You can change it later in iPhone Mirroring → Settings.
5. When the window shows your phone's screen, you're connected. Lock the phone and keep it near the Mac.

## Give the AI client access

- **Accessibility**: System Settings → Privacy & Security → Accessibility; turn it on for your AI client (or for the terminal it runs in).
- **Screen & System Audio Recording** (called Screen Recording on older macOS): same page, same app. You may need to restart the app afterwards.
- **The client's own switch**: this skill can't turn on Computer Use by itself. Turn it on in the client (names and places vary; follow its docs) and allow it to control iPhone Mirroring. Some clients run Computer Use through a separate helper app (Codex does), so the permission prompt may name that helper. Some ask for approval the first time they act.
- You turn these on yourself. The AI shouldn't change system settings for you.

## For "write on the Mac, paste on the phone": turn on Handoff

Copying on the Mac and pasting on the iPhone uses Apple's Universal Clipboard, which needs Handoff on both devices:

- Mac: System Settings → General → AirDrop & Handoff → allow Handoff.
- iPhone: Settings → General → AirPlay & Continuity → Handoff.

Menu names can differ slightly between versions. Files and images can also be dragged between the Mac and the mirroring window.

## Before a long task

- Plug in the phone and leave it locked; StandBy while charging is fine.
- Plug in the Mac and keep it from sleeping.
- A Focus mode on the Mac cuts down on notification banners covering the mirror.
- Sign in to the apps on the phone beforehand, so the task doesn't stall at a login.

## If it won't connect

Following Apple's troubleshooting, done by you:

1. Check the requirements above: devices close together, Bluetooth and Wi-Fi on.
2. Make sure the phone is locked. After a restart, unlock it once, then lock it.
3. Check VPNs and third-party security software on both devices; the Mac's firewall shouldn't block all incoming connections.
4. Revoke access to the iPhone in iPhone Mirroring settings, then set it up again.
5. If it still fails, see Apple's article for the remaining steps and decide for yourself. The AI shouldn't change your account or security settings.
