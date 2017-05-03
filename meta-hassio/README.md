﻿# ResinOS - HassIO Image
The image is based on ResinOS and Yocto Linux. It comes with the HassIO supervisor pre-installed. This includes support to update the supervisor over the air. After flashing your host OS will not require any more maintenance! The image does not include Home Assistant, instead it will downloaded when the image boots up for the first time.

Download can be found here: https://drive.google.com/drive/folders/0B2o1Uz6l1wVNbFJnb2gwNXJja28?usp=sharing

After extracting the archive, flash it to a drive using [Etcher](https://etcher.io/).

## History
- **0.1**: First techpreview with dumy supervisor (ResinOS 2.0.0-RC5)
- **0.2**: Fix some bugs and update it to HassIO 0.2
- **0.3**: Update HostControl and feature for HassIO 0.3 (ResinOS 2.0.0 / need reflash)
- **0.4**: Update HostControl and bring resinos OTA (resinhub) back (ResinOS 2.0.0-rev3)
- **0.5**: Update HostControl and new GIT repository (HassIO 0.14)
- **0.6**: Update to new docker hub from homeassistant (HassIO 0.18) (ResinOS 2.0.2) -> *Need reflash!* 

## Configuring the image
You can configure the WiFi network that the image should connect to after flashing using [`resin-device-toolbox`](https://resinos.io/docs/raspberrypi3/gettingstarted/#install-resin-device-toolbox).

## Developer access to ResinOS host
Create an `authorized_keys` file in the boot partition of your SD card with your public key. After a boot it, you can acces your device as root over ssh on port 22222.

## Troubleshooting

Read logoutput from supervisor:
```bash
journalctl -f -u resin-supervisor.service
docker logs homeassistant
```