# i2pgram client for desktop

```
<Дремучесть> x, и2п клиент для десткопа ща дам
<Дремучесть> на цпп qt
<Дремучесть> https://github.com/i2pgram/i2pgram-desktop/blob/dev1/Telegram/SourceFiles/main.cpp#L277
<Дремучесть> https://github.com/i2pgram/i2pgram-desktop
<Дремучесть> я там комманд лайн опции добавил
<Дремучесть> вот print_usage() 
https://github.com/i2pgram/i2pgram-desktop/blob/dev1/Telegram/SourceFiles/main.cpp#L120
<x> а как собтирать?
<Дремучесть> вот устаревшая билд дока 
https://github.com/i2pgram/i2pgram-clients/blob/master/tdesktop/BUILD_INSTRUCTIONS.md
<Дремучесть> и вот оригинальная телеграмовская
https://github.com/i2pgram/i2pgram-desktop/blob/dev1/docs/building-cmake.md
<Дремучесть> нада привести в порядок билд доку
<x> че 14.04 надо ставить что ли?
<Дремучесть> сборщик клиента да на древней убунте
<Дремучесть> работает типа на всех новее
<Дремучесть> экзешник

<Дремучесть> dc host port можно 127.0.0.1 указывать, пашет мы проверяли
<Дремучесть> но группу мы не создавали
<Дремучесть> но коннектится и чёта там шлёт
<Дремучесть> успешно логинится
<Дремучесть> вот эти два публ. ключа проносятся в потрох телеги тут 
https://github.com/i2pgram/i2pgram-desktop/blob/dev1/Telegram/SourceFiles/main.cpp#L150
<Дремучесть> MTP::setRSAPubKey(index, strdup(buf.c_str()));
<Дремучесть> ща примеры пуб.ключей дам
<Дремучесть> вот какие-то https://github.com/i2pgram/i2pgram-clients/blob/master/tdesktop/dc_options.cpp.diff

<Дремучий_Шаман> для i2pgram ключики тут есть https://github.com/PluralityNET/PluralityServer/tree/master/sample-keys/nebula-sample-dc-keys
<Дремучий_Шаман> это из патчей небулы
<Дремучий_Шаман> ключи
<x> Дремучий_Шаман, это те которые из апстрима или ваши собственные?
<Дремучий_Шаман> это копипаста из небулы
<Дремучий_Шаман> из апстрима
```

OLDER INFO BELOW

This is the complete source code and the build instructions for the alpha version of the official desktop client for the [Telegram][telegram] messenger, based on the [Telegram API][telegram_api] and the [MTProto][telegram_proto] secure protocol.

[![Version](https://badge.fury.io/gh/telegramdesktop%2Ftdesktop.svg)](https://github.com/telegramdesktop/tdesktop/releases)
[![Build Status](https://travis-ci.org/telegramdesktop/tdesktop.svg?branch=dev)](https://travis-ci.org/telegramdesktop/tdesktop)
[![Build status](https://ci.appveyor.com/api/projects/status/uiw2y768iy4i5bu8/branch/dev?svg=true)](https://ci.appveyor.com/project/telegramdesktop/tdesktop)

[![Preview of Telegram Desktop][preview_image]][preview_image_url]

The source code is published under GPLv3 with OpenSSL exception, the license is available [here][license].

## Supported systems

* Windows XP - Windows 10 (**not** RT)
* Mac OS X 10.8 - Mac OS X 10.11
* Mac OS X 10.6 - Mac OS X 10.7 (separate build)
* Ubuntu 12.04 - Ubuntu 18.04
* Fedora 22 - Fedora 28
* [Snappy](https://snapcraft.io/telegram-desktop)

## Third-party

* Qt 5.3.2 and 5.6.2, slightly patched ([LGPL](http://doc.qt.io/qt-5/lgpl.html))
* OpenSSL 1.0.1g ([OpenSSL License](https://www.openssl.org/source/license.html))
* zlib 1.2.8 ([zlib License](http://www.zlib.net/zlib_license.html))
* libexif 0.6.20 ([LGPL](https://www.gnu.org/licenses/old-licenses/lgpl-2.1.en.html))
* LZMA SDK 9.20 ([public domain](http://www.7-zip.org/sdk.html))
* liblzma ([public domain](http://tukaani.org/xz/))
* Google Breakpad ([License](https://chromium.googlesource.com/breakpad/breakpad/+/master/LICENSE))
* Google Crashpad ([Apache License 2.0](https://chromium.googlesource.com/crashpad/crashpad/+/master/LICENSE))
* GYP ([BSD License](https://github.com/bnoordhuis/gyp/blob/master/LICENSE))
* Ninja ([Apache License 2.0](https://github.com/ninja-build/ninja/blob/master/COPYING))
* OpenAL Soft ([LGPL](https://github.com/kcat/openal-soft/blob/master/COPYING))
* Opus codec ([BSD License](http://www.opus-codec.org/license/))
* FFmpeg ([LGPL](https://www.ffmpeg.org/legal.html))
* Guideline Support Library ([MIT License](https://github.com/Microsoft/GSL/blob/master/LICENSE))
* Mapbox Variant ([BSD License](https://github.com/mapbox/variant/blob/master/LICENSE))
* Range-v3 ([Boost License](https://github.com/ericniebler/range-v3/blob/master/LICENSE.txt))
* Open Sans font ([Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html))
* Emoji alpha codes ([MIT License](https://github.com/emojione/emojione/blob/master/extras/alpha-codes/LICENSE.md))
* Catch test framework ([Boost License](https://github.com/philsquared/Catch/blob/master/LICENSE.txt))
* xxHash ([BSD License](https://github.com/Cyan4973/xxHash/blob/dev/LICENSE))

## Build instructions

* [Visual Studio 2017][msvc]
* [Xcode 9][xcode]
* [GYP/CMake on GNU/Linux][cmake]

[//]: # (LINKS)
[telegram]: https://telegram.org
[telegram_desktop]: https://desktop.telegram.org
[telegram_api]: https://core.telegram.org
[telegram_proto]: https://core.telegram.org/mtproto
[license]: LICENSE
[msvc]: docs/building-msvc.md
[xcode]: docs/building-xcode.md
[xcode_old]: docs/building-xcode-old.md
[cmake]: docs/building-cmake.md
[preview_image]: https://github.com/telegramdesktop/tdesktop/blob/dev/docs/assets/preview.png "Preview of Telegram Desktop"
[preview_image_url]: https://raw.githubusercontent.com/telegramdesktop/tdesktop/dev/docs/assets/preview.png
