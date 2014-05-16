gamepadmapping.js is a JavaScript library for use with the [Gamepad API]. Unfortunately there's very little consistency between how different game controllers expose their buttons and axes, so it's hard to allow users to use the controllers they have without a tedious manual configuration step. The API does define a [standard mapping] and browser vendors do ship with mappings for some devices to map to the standard mapping, but it seems unlikely that there will ever be 100% coverage of devices in the wild, and users using new devices with slightly outdated browsers are still out of luck.

This library intends to help lessen the problem by providing easy access to a [database of known controller mappings] and remapping controllers that it knows about to the standard mapping.

Usage
=====

This library provides two methods, exposed on `window`:
* `getGamepads()`: Returns an Array of connected gamepads, as from `navigator.getGamepads()`, but with controls mapped to the [standard mapping] if possible.
* `remapGamepad(gamepad)`: Given a `Gamepad` object, remap it to the standard mapping if possible. If not possible the input gamepad will be returned.

[Gamepad API]: https://dvcs.w3.org/hg/gamepad/raw-file/default/gamepad.html
[standard mapping]: https://dvcs.w3.org/hg/gamepad/raw-file/default/gamepad.html#remapping
[database of known controller mappings]: https://github.com/luser/gamepad-data
