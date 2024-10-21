# unicorne-lp
flash file and json for unicorne lp keymap

# Configure keymap
- upload json to https://config.qmk.fm/#/boardsource/unicorne/LAYOUT_split_3x6_3
- modify then create firmware

# Flash instructions
Each side must be flashed individually. 
- Unplug the two halves from each other
- Unplug the left side from the computer
- While holding the top left key on the left half, plug in the left half.
- You should see the keyboard enter boot mode
- drag .utf2 file into keyboard drive
- board should reboot
- Repeat for right half, but hold top right key while plugging it in

# Mouse drift
Boardsource has [docs](https://www.boardsource.xyz/docs/build_guides-unicorne) saying there may be issues with mouse drift. QMK Configurator doesn't support adding their suggested fix. Use the configurator to update the keymap, then paste the new json at https://compile.qmk.fm/ and add the following to the json: 
```json
    "config": {
        "features": {
            "pointing_device": false
        }
    }
```
Use the same site to compile the firmware then repeat the flash instructions above.
