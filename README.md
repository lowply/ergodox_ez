# ErgoDox EZ Configuration for lowply

- Doc: [Introduction](https://docs.qmk.fm/#/newbs)
- Repo: [qmk/qmk_firmware: Open-source keyboard firmware for Atmel AVR and Arm USB families](https://github.com/qmk/qmk_firmware)

```
brew install qmk/qmk/qmk
ghq get git@github.com:qmk/qmk_firmware.git
# cd to the repo
qmk config user.keyboard=ergodox_ez
```

Symlink my keymap:

```
ln -s ~/ghq/github.com/lowply/ergodox_ez keyboards/ergodox_ez/keymaps/lowply
```

Or, create a new keymap and update the `keymap.c` file:

```
qmk new-keymap
> Keyboard Name: ergodox_ez
> Keymap Name: lowply
vim keyboards/ergodox_ez/keymaps/lowply/keymap.c
```

Then compile it. The output will look like this:

```
$ qmk compile -kb ergodox_ez -km lowply
Ψ Compiling keymap with gmake --jobs=1 ergodox_ez:lowply


QMK Firmware 0.15.21
WARNING: Some git submodules are out of date or modified.
 Please consider running make git-submodule.

Making ergodox_ez with keymap lowply

avr-gcc (Homebrew AVR GCC 9.3.0_3) 9.3.0
Copyright (C) 2019 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

Compiling: keyboards/ergodox_ez/matrix.c                                                            [OK]
Compiling: keyboards/ergodox_ez/led_i2c.c                                                           [OK]
Compiling: keyboards/ergodox_ez/ergodox_ez.c                                                        [OK]
Compiling: keyboards/ergodox_ez/keymaps/lowply/keymap.c                                             [OK]
Compiling: quantum/quantum.c                                                                        [OK]
Compiling: quantum/send_string.c                                                                    [OK]
Compiling: quantum/bitwise.c                                                                        [OK]
Compiling: quantum/led.c                                                                            [OK]
Compiling: quantum/action.c                                                                         [OK]
Compiling: quantum/action_layer.c                                                                   [OK]
Compiling: quantum/action_macro.c                                                                   [OK]
Compiling: quantum/action_tapping.c                                                                 [OK]
Compiling: quantum/action_util.c                                                                    [OK]
Compiling: quantum/eeconfig.c                                                                       [OK]
Compiling: quantum/keyboard.c                                                                       [OK]
Compiling: quantum/keymap_common.c                                                                  [OK]
Compiling: quantum/keycode_config.c                                                                 [OK]
Compiling: quantum/sync_timer.c                                                                     [OK]
Compiling: quantum/logging/debug.c                                                                  [OK]
Compiling: quantum/logging/sendchar.c                                                               [OK]
Compiling: quantum/bootmagic/magic.c                                                                [OK]
Compiling: quantum/matrix_common.c                                                                  [OK]
Compiling: quantum/debounce/sym_eager_pr.c                                                          [OK]
Compiling: quantum/main.c                                                                           [OK]
Compiling: quantum/mousekey.c                                                                       [OK]
Compiling: quantum/process_keycode/process_magic.c                                                  [OK]
Compiling: quantum/process_keycode/process_grave_esc.c                                              [OK]
Compiling: quantum/process_keycode/process_space_cadet.c                                            [OK]
Compiling: platforms/avr/drivers/i2c_master.c                                                       [OK]
Archiving: .build/obj_ergodox_ez_lowply/i2c_master.o                                                [OK]
Assembling: platforms/avr/xprintf.S                                                                 [OK]
Compiling: platforms/avr/printf.c                                                                   [OK]
Compiling: tmk_core/protocol/host.c                                                                 [OK]
Compiling: tmk_core/protocol/report.c                                                               [OK]
Compiling: tmk_core/protocol/usb_device_state.c                                                     [OK]
Compiling: tmk_core/protocol/usb_util.c                                                             [OK]
Compiling: platforms/avr/platform.c                                                                 [OK]
Compiling: platforms/avr/suspend.c                                                                  [OK]
Compiling: platforms/avr/timer.c                                                                    [OK]
Compiling: platforms/avr/bootloader.c                                                               [OK]
Compiling: tmk_core/protocol/lufa/lufa.c                                                            [OK]
Compiling: tmk_core/protocol/usb_descriptor.c                                                       [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Class/Common/HIDParser.c                                       [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/AVR8/Device_AVR8.c                                        [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/AVR8/EndpointStream_AVR8.c                                [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/AVR8/Endpoint_AVR8.c                                      [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/AVR8/Host_AVR8.c                                          [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/AVR8/PipeStream_AVR8.c                                    [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/AVR8/Pipe_AVR8.c                                          [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/AVR8/USBController_AVR8.c                                 [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/AVR8/USBInterrupt_AVR8.c                                  [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/ConfigDescriptors.c                                       [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/DeviceStandardReq.c                                       [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/Events.c                                                  [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/HostStandardReq.c                                         [OK]
Compiling: lib/lufa/LUFA/Drivers/USB/Core/USBTask.c                                                 [OK]
Compiling: tmk_core/protocol/lufa/usb_util.c                                                        [OK]
Linking: .build/ergodox_ez_lowply.elf                                                               [OK]
Creating load file for flashing: .build/ergodox_ez_lowply.hex                                       [OK]
Copying ergodox_ez_lowply.hex to qmk_firmware folder                                                [OK]
Checking file size of ergodox_ez_lowply.hex                                                         [OK]
 * The firmware size is fine - 19906/32256 (61%, 12350 bytes free)
```

- Note that you'll need `avr-gcc`
- If it fails with `No rule to make target 'drivers/avr/i2c_master.c'`, try `qmk clean` and compile again.

And apply while the keyboard is connected:

```
qmk flash -kb ergodox_ez -km lowply
[Send RESET by hitting Fn + `]
```

There's a GUI tool [qmk_toolbox](https://github.com/qmk/qmk_toolbox) but CLI is much easier.
