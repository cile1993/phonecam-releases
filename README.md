# PhoneCam downloads

Turn an Android phone into a low latency webcam for Windows, over your local
network. It appears as a real camera device, so Chrome, Zoom, Teams, Discord and
OBS can select it like any other webcam.

**[Download the latest version](../../releases/latest)**

This repository exists only to host the downloads. The source lives elsewhere.

## What gets installed

Two things, and both are needed:

- **PhoneCam receiver**, the desktop app that connects to your phone.
- **PhoneCam Virtual Camera**, a Windows camera device. This is the part that
  makes the phone appear in other applications as an ordinary webcam.

The installer registers the camera, so it asks for administrator rights once.
Uninstalling removes it again.

## Getting started

1. Install PhoneCam on the computer and run it. It shows a QR code.
2. Open the PhoneCam app on your phone and tap **Scan QR code**.
3. In whatever application you want to use, pick **PhoneCam Virtual Camera**.

If the phone is on the same Wi-Fi it will usually find the computer by itself,
and you can skip the QR code entirely.

## Requirements

- Windows 10 version 2004 or newer, 64 bit. The virtual camera uses an API that
  does not exist in earlier versions.
- An Android phone on the same Wi-Fi network.

## Known limitations

- **Windows warns on first run.** The installer is not code signed yet, so
  SmartScreen shows "Windows protected your PC". Choose **More info**, then
  **Run anyway**. A signing certificate is on the list.
- **One application at a time** can use the virtual camera.
- Your phone's camera decides the maximum frame rate. Many phones cap at 30 fps
  regardless of what is selected.

## Privacy

Everything stays on your local network. There is no account, no cloud service,
and no telemetry. The apps make no external network calls at all: video and audio
go straight from the phone to the computer over your own Wi-Fi, encrypted by
WebRTC.

## Verifying a download

Each release lists a SHA256 checksum.

```powershell
Get-FileHash .\PhoneCam-Setup-0.3.0.exe -Algorithm SHA256
```

## Licence

PhoneCam is proprietary software. Installing and using it is free; redistributing
it, reselling it or reverse engineering it is not. The full terms are shown
during installation and are included with the installed files.

It is built on open source components, all permissively licensed, whose notices
ship alongside the application.
