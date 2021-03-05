# Keychron K8
Use this information at your own discretion and risk.

This is for K8 RGB v1 ANSI. (Hardware Supported: SN32F248BF)

**Progress:**
- QMK custom keymaps are working properly
- RGB does not work, have it completely disabled for now
- Bluetooth does not work, currently waiting for QMK to release an official Bluetooth API
- VIA does not work, will softbrick your keyboard

**Setup repo + dependencies**
1. Clone this repository: https://github.com/SonixQMK/qmk_firmware
2. `git submodule add https://github.com/SonixQMK/ChibiOS-Contrib.git`
3. `make git-submodule`
4. Copy keyboards/keychron/k8/ from this repository over to your qmk_firmware directory
5. You should be able to compile now

**Instructions on how to flash QMK to the K8:**
1. Customize your keymap and compile your firmware (`make keychron/k8:default`)
2. Download this flashing tool and run it: https://github.com/qmk/qmk_firmware/files/5862715/SONiX_USB_MCU_ISP_Tool_V2.3.1.7-.zip
3. Click 'Load File' and select `SN32F24xB` on the right, then choose your *.hex QMK firmware file
4. VID - `0C45`, PID - `7040`
5. Put your K8 into DFU/bootloader mode:
    - Remove the spacebar and short the `BOOT` pin to `P7` pin
    - Note: There are 5 pins on the left of the spacebar switch, `BOOT` and `P7` are the two rightmost pins
6. Connect your K8 to your computer
7. Click 'Flash' in the Sonix flashing tool
8. Enjoy