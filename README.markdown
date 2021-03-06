# CSSJanus

Flips CSS from LTR to an RTL orientation and vice-versa

## Introduction

CSSJanus is CSS parser utility designed to aid the conversion of a website's layout from left-to-right(LTR) to right-to-left(RTL). The script was born out of a need to convert CSS for RTL languages when tables are not being used for layout (since tables will automatically reorder TD's in RTL).

CSSJanus will change most of the obvious CSS property names and their values as well as some not-so-obvious ones (cursor, background-position %, etc...). The script is designed to offer flexibility to account for cases when you do not want to change certain rules which exist to account for bidirectional text display bugs, as well as situations where you may or may not want to flip annotations inside of the background url string.

Note that you can disable CSSJanus from running on an entire class or any rule within a class by prepending a /* @noflip */ comment before the rule(s) you want CSSJanus to ignore.

CSSJanus itself is not always enough to make a website that works in a LTR language context work in a RTL language all the way, but it is a start.

## Getting the code

View the trunk at:

    http://cssjanus.googlecode.com/svn/trunk/

Check out the latest development version anonymously with:

    $ svn checkout http://cssjanus.googlecode.com/svn/trunk/ cssjanus

## Using

Usage:

    ./cssjanus.py < file.css > file-rtl.css

Flags:

    --swap_left_right_in_url: Fixes "left"/"right" string within urls.
    Ex: ./cssjanus.py --swap_left_right_in_url < file.css > file_rtl.css

    --swap_ltr_rtl_in_url: Fixes "ltr"/"rtl" string within urls.
    Ex: ./cssjanus.py --swap_ltr_rtl_in_url < file.css > file_rtl.css

    --ignore_bad_bgp: Ignores unmirrorable background-position values.
    Ex: ./cssjanus.py --ignore_bad_bgp < file.css > file_rtl.css

If you'd like to make use of the webapp version of cssjanus, you'll need to download the Google App Engine SDK, http://code.google.com/appengine/downloads.html, and also drop a "django" directory into this directory, with the latest svn from django. You should be good to go with that setup. Please let me know otherwise.

## Bugs, Patches

Patches and bug reports are welcome, just please keep the style consistent with the original source. If you find a bug, please include a diff of cssjanus_test.py with the bug included as a new unit test which fails. It will make understanding and fixing the bug easier.

## Todo

* Include some helpers for some typical bidi text solutions?
* Aural CSS (azimuth) swapping?

## Author

Lindsey Simon <elsigh@google.com>

## Contributors

Additional thanks to Mike Samuel for his work on csslex.py, Andy Perelson for his help coding and reviewing, Stephen Zabel for his help with i18n and my sanity, and to Eric Meyer for his thoughtful input.

Thanks to Junyu Wang for the Chinese translation.
Thanks to Masashi Kawashima for the Japanese translation.
Thanks to Taaryk Taar and Tariq Al-Omaireeni for an updated Arabic translation.
Thanks to Jens Meiert for the German translation.
Thanks to דור דנקנר for the Hebrew translation.

## License

    Copyright 2008 Google Inc. All Rights Reserved.

    Licensed under the Apache License, Version 2.0 (the 'License');
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an 'AS IS' BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

