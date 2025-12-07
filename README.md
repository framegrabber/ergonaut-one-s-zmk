# ZMK Firmware for Ergonaut One S keyboard

This is a repository for a ZMK Firmware for Ergonaut One S keyboard.

## Custom keymap

Visual representation of my customized keymap in keymap-drawer: [keymap-drawer.streamlit.app](https://keymap-drawer.streamlit.app/?zmk_url=https%3A%2F%2Fgithub.com%2Fframegrabber%2Fergonaut-one-s-zmk%2Fblob%2Fmain%2Fconfig%2Fergonaut_one_s.keymap)

This layout is heavily inspired by [Miryoku layout](https://github.com/manna-harbour/miryoku)

## FAQ

- [FAQ](#faq)
  - [How to change the keymap?](#how-to-change-the-keymap)
  - [How to flash the keyboard?](#how-to-flash-the-keyboard)
  - [How to pair halves?](#how-to-pair-halves)
  - [Problems](#problems)
    - [I'm getting File Transfer Error after copying firmware to the keyboard](#im-getting-file-transfer-error-after-copying-firmware-to-the-keyboard)

### How to change the keymap?

1. Fork or use this repository as a template https://github.com/ergonautkb/one-s-zmk-config.
2. Enable Github Actions for your repository if needed.

You have two options on how to configure your desired keymap:

#### Option 1. Keymap Editor

1. Open [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/).
2. Connect it to your Github account and give an access to your repository to Keymap Editor's app.
3. Make changes to your keymap and press `Save` - it will trigger software build. Wait for it to complete.
4. Grab the `firmware.zip` archive.

#### Option 2. Manual

1. Make changes to the [ergonaut_one.keymap](config/boards/shields/ergonaut_one_s/ergonaut_one_s.keymap) file using your favorite text editor.
2. Commit changes to your repository.
3. Go to `Actions` tab in your Github repository, locate the latest build and wait for it to complete.
4. Grab the `firmware.zip` archive

### How to flash the keyboard?

1. Obtain `firmware.zip`
2. Unzip `firmware.zip` - you should have `ergonaut_one_s_left-seeeduino_xiao_ble-zmk.uf2` and `ergonaut_one_s_right-seeeduino_xiao_ble-zmk.uf2` files
3. Turn off the power for selected halve (move slider to position `OFF`)
4. Connect selected halve to the PC via USB-C cable
5. Press `RESET` button **twice** to enter DFU mode - you should see new USB device in your file manager
6. Copy the corresponding firmware to the root directory of the new USB device
7. Disconnect selected halve from the PC
8. Repeat steps 3-7 for the other halve

### How to pair halves?

1. Turn off the power for both halves (move slider to position `OFF`)
2. Turn on the power for both halves (move slider to position `ON`)
3. Press `RESET` button **once** on both halves **simultaneously**

### Problems

#### I'm getting File Transfer Error after copying firmware to the keyboard

It's OK. Proof: https://zmk.dev/docs/troubleshooting#file-transfer-error
