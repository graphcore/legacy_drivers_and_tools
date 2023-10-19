# Legacy Hardware

The hardware referenced in this repository is no longer supported by Graphcore. Information and tools are provided here without warranty or support in the hope that they will be useful to hobbyists and computer historians.

Please see the LICENSE file and read the EULA document before using the software: [EULA](EULA.md).

This repository contains information and tools for the legacy products listed below:

## Graphcore C2 PCIe card

Graphcore’s dual IPU PCIe card with two GC2 Colossus IPUs. The GC2 was Graphcore's first (Mk1) chip. The card provides performance of 250 TFLOPS/s of mixed precision compute with 192 GB/s IPU-Link bandwidth between IPUs, 128 GB/s card to card IPU-Links. Maximum power consumption is 300 W.

&#9888; The C2 card was designed for use in data centres and requires active cooling. The chassis fans must provide sufficient airflow through the fins to keep it operating safely at peak performance.

C2 Resources available:
 - [Firmware](c2/tools)
 - [Docs](c2/docs)
 - [License](c2/LICENSE)

### Instructions

The icuflash tarball contains a document describing how to use the icuflash tool.

You need to complete the checks in the “Before Starting” section before upgrading the firmware.

The commands that correspond to steps 1 to 5 for upgrading from 1.3.XX firmware to 1.4.14 firmware for all attached C2 cards are the following:

#### Step 1 Install one of the two v1.4.14 images to the ICU and reboot into it.
./icuflash image -a -f
sudo reboot

#### Step 2 Install both public keys to the ICU.
./icuflash keys --update -k 0 -a -f
./icuflash keys --update -k 1 -a -f

#### Step 3 Install the other of the two v1.4.14 images to the ICU and reboot into it.
./icuflash image -a -f
sudo reboot

#### Steps 4 and 5 Re-install the original upgrade image
./icuflash image -a -f
sudo reboot
