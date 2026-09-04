# Controller Mapping

Source-reviewed snapshot: **2026-09-03**. The hosted shell, EmuHub wheel, and
native runtime have different input ownership. A remote working in the wheel
does not prove that a Bluetooth gamepad is mapped correctly inside every core.

## TV shell

Use the TV remote's directions and confirmation control to navigate the hosted
UI. The boot shell accepts Enter to skip its startup video; Back/Escape returns
through the platform's back action. The EmuHub settings panel provides explicit
Stop, return, and Exit actions. Prefer those visible actions over guessing a
universal hotkey combination. Stop/Exit behavior must be qualified per TV model.

## 8BitDo SF30 Pro, SDL GameController profile

The inspected `8Bitdo_SF30_Pro_webOS.cfg` targets the SDL GameController mapping,
not raw Linux event indices. These indices must not be copied into the iOS or
Fire TV input layer.

| Logical input | SDL button / axis |
| --- | --- |
| RetroPad B / A / Y / X | Buttons 0 / 1 / 2 / 3 |
| Select / Start | Buttons 4 / 6 |
| Menu / Home | Button 5 |
| L3 / R3 | Buttons 7 / 8 |
| L / R shoulders | Buttons 9 / 10 |
| Up / Down / Left / Right | Buttons 11 / 12 / 13 / 14 |
| L2 / R2 triggers | Positive axes 4 / 5 |
| Left stick X / Y | Axes 0 / 1, both signs |
| Right stick X / Y | Axes 2 / 3, both signs |

This fixes the **configuration-level** Select/Start/stick-index distinction.
Owner-visible coin, Start, stick clicks, diagonals, and reconnect behavior still
require physical acceptance with the installed package. Different 8BitDo modes,
firmware, or controller models can expose different device profiles.

## Guest console mapping

The selected core translates RetroPad positions into original console inputs.
Do not assume that an SF30's printed Nintendo letter equals a PlayStation
button. Arcade Coin normally uses Select, while Start begins the game; confirm
the active core's profile and player port. Six-button Sega systems and numeric
keypads need their own core-specific translation, not a generic four-button map.

## Before reporting support

Record TV model, OS, complete installed bundle, core, controller connection mode,
and game. Test every button and axis, simultaneous inputs, menu isolation,
disconnect/reconnect, Stop, and a second launch. Never infer universal gamepad
support from native core package coverage.
