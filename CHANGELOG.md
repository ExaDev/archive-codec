# 1.0.0 (2026-08-17)


### Features

* archive-format detection from magic bytes (zip vs unknown) ([2fb4349](https://github.com/ExaDev/archive-codec/commit/2fb4349b2c8f69c379fb07cb140bea1405bb8b2d))
* recursive zip-in-zip walking with depth and cumulative decompressed-size guards ([5eed470](https://github.com/ExaDev/archive-codec/commit/5eed470d307c3414a008d79ab117c1d9fb7c41f2))
* zip container read/write over fflate with ordered-entry emission control ([acf571c](https://github.com/ExaDev/archive-codec/commit/acf571c73684626ecf973d2e466ec0b2dce906d5))
