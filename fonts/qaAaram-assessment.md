## Fontbakery report

Fontbakery version: 0.7.31

<details>
<summary><b>[18] Aaram-Regular.ttf</b></summary>
<details>
<summary>🔥 <b>FAIL:</b> Check `Google Fonts Latin Core` glyph coverage.</summary>

* [com.google.fonts/check/glyph_coverage](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/glyph_coverage)
<pre>--- Rationale ---

Google Fonts expects that fonts in its collection support at least the minimal
set of characters defined in the `GF-latin-core` glyph-set.


</pre>

* 🔥 **FAIL** Missing required codepoints: 0x2215 (DIVISION SLASH) [code: missing-codepoints]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Check license file has good copyright string.</summary>

* [com.google.fonts/check/license/OFL_copyright](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/license/OFL_copyright)
<pre>--- Rationale ---

An OFL.txt file&#x27;s first line should be the font copyright e.g:
&quot;Copyright 2019 The Montserrat Project Authors
(https://github.com/julietaula/montserrat)&quot;


</pre>

* 🔥 **FAIL** First line in license file does not match expected format: "copyright (c) 2014, tharique azeez (http://niram.org|zeezat@gmail.com)"

</details>
<details>
<summary>🔥 <b>FAIL:</b> Copyright notices match canonical pattern in fonts</summary>

* [com.google.fonts/check/font_copyright](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/font_copyright)

* 🔥 **FAIL** Name Table entry: Copyright notices should match a pattern similar to: "Copyright 2019 The Familyname Project Authors (git url)"
But instead we have got:
"Copyright (c) 2014 by Tharique Azeez. All rights reserved." [code: bad-notice-format]
* 🔥 **FAIL** Name Table entry: Copyright notices should match a pattern similar to: "Copyright 2019 The Familyname Project Authors (git url)"
But instead we have got:
"Copyright (c) 2014 by Tharique Azeez. All rights reserved." [code: bad-notice-format]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Checking OS/2 fsSelection value.</summary>

* [com.google.fonts/check/fsselection](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/fsselection)

* 🔥 **FAIL** OS/2 fsSelection REGULAR bit should be set. [code: bad-REGULAR]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Font enables smart dropout control in "prep" table instructions?</summary>

* [com.google.fonts/check/smart_dropout](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/smart_dropout)
<pre>--- Rationale ---

This setup is meant to ensure consistent rendering quality for fonts across all
devices (with different rendering/hinting capabilities).

Below is the snippet of instructions we expect to see in the fonts:
B8 01 FF    PUSHW 0x01FF
85          SCANCTRL (unconditinally turn on
                      dropout control mode)
B0 04       PUSHB 0x04
8D          SCANTYPE (enable smart dropout control)

&quot;Smart dropout control&quot; means activating rules 1, 2 and 5:
Rule 1: If a pixel&#x27;s center falls within the glyph outline,
        that pixel is turned on.
Rule 2: If a contour falls exactly on a pixel&#x27;s center,
        that pixel is turned on.
Rule 5: If a scan line between two adjacent pixel centers
        (either vertical or horizontal) is intersected
        by both an on-Transition contour and an off-Transition
        contour and neither of the pixels was already turned on
        by rules 1 and 2, turn on the pixel which is closer to
        the midpoint between the on-Transition contour and
        off-Transition contour. This is &quot;Smart&quot; dropout control.

For more detailed info (such as other rules not enabled in this snippet),
please refer to the TrueType Instruction Set documentation.


</pre>

* 🔥 **FAIL** The 'prep' table does not contain TrueType instructions enabling smart dropout control. To fix, export the font with autohinting enabled, or run ttfautohint on the font, or run the `gftools fix-nonhinting` script. [code: lacks-smart-dropout]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Checking OS/2 usWinAscent & usWinDescent.</summary>

* [com.google.fonts/check/family/win_ascent_and_descent](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/family/win_ascent_and_descent)
<pre>--- Rationale ---

A font&#x27;s winAscent and winDescent values should be greater than the head
table&#x27;s yMax, abs(yMin) values. If they are less than these values, clipping
can occur on Windows platforms
(https://github.com/RedHatBrand/Overpass/issues/33).

If the font includes tall/deep writing systems such as Arabic or Devanagari,
the winAscent and winDescent can be greater than the yMax and abs(yMin) to
accommodate vowel marks.

When the win Metrics are significantly greater than the upm, the linespacing
can appear too loose. To counteract this, enabling the OS/2 fsSelection bit 7
(Use_Typo_Metrics), will force Windows to use the OS/2 typo values instead.
This means the font developer can control the linespacing with the typo values,
whilst avoiding clipping by setting the win values to values greater than the
yMax and abs(yMin).


</pre>

* 🔥 **FAIL** OS/2.usWinAscent value should be equal or greater than 974, but got 971 instead [code: ascent]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Checking OS/2 Metrics match hhea Metrics.</summary>

* [com.google.fonts/check/os2_metrics_match_hhea](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/os2_metrics_match_hhea)
<pre>--- Rationale ---

When OS/2 and hhea vertical metrics match, the same linespacing results on
macOS, GNU+Linux and Windows. Unfortunately as of 2018, Google Fonts has
released many fonts with vertical metrics that don&#x27;t match in this way. When we
fix this issue in these existing families, we will create a visible change in
line/paragraph layout for either Windows or macOS users, which will upset some
of them.

But we have a duty to fix broken stuff, and inconsistent paragraph layout is
unacceptably broken when it is possible to avoid it.

If users complain and prefer the old broken version, they have the freedom to
take care of their own situation.


</pre>

* 🔥 **FAIL** OS/2 sTypoAscender (750) and hhea ascent (971) must be equal. [code: ascender]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Glyph names are all valid?</summary>

* [com.google.fonts/check/valid_glyphnames](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/valid_glyphnames)
<pre>--- Rationale ---

Microsoft&#x27;s recommendations for OpenType Fonts states the following:

&#x27;NOTE: The PostScript glyph name must be no longer than 31 characters, include
only uppercase or lowercase English letters, European digits, the period or the
underscore, i.e. from the set [A-Za-z0-9_.] and should start with a letter,
except the special glyph name &quot;.notdef&quot; which starts with a period.&#x27;

https://docs.microsoft.com/en-us/typography/opentype/spec/recom#post-table


In practice, though, particularly in modern environments, glyph names can be as
long as 63 characters.
According to the &quot;Adobe Glyph List Specification&quot; available at:

https://github.com/adobe-type-tools/agl-specification


</pre>

* 🔥 **FAIL** The following glyph names do not comply with naming conventions: uni00AD#1

 A glyph name must be entirely comprised of characters from the following set: A-Z a-z 0-9 .(period) _(underscore). A glyph name must not start with a digit or period. There are a few exceptions such as the special glyph ".notdef". The glyph names "twocents", "a1", and "_" are all valid, while "2cents" and ".twocents" are not. [code: found-invalid-names]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Font contains unique glyph names?</summary>

* [com.google.fonts/check/unique_glyphnames](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/unique_glyphnames)
<pre>--- Rationale ---

Duplicate glyph names prevent font installation on Mac OS X.


</pre>

* 🔥 **FAIL** The following glyph names occur twice: ['uni00AD']

</details>
<details>
<summary>🔥 <b>FAIL:</b> Ensure indic fonts have the Indian Rupee Sign glyph. </summary>

* [com.google.fonts/check/rupee](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/rupee)
<pre>--- Rationale ---

Per Bureau of Indian Standards every font supporting one of the official Indian
languages needs to include Unicode Character “₹” (U+20B9) Indian Rupee Sign.


</pre>

* 🔥 **FAIL** Please add a glyph for Indian Rupee Sign “₹” at codepoint U+20B9. [code: missing-rupee]

</details>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---

Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is
stored in the achVendID field of the OS/2 table.

Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:

https://docs.microsoft.com/en-us/typography/vendors/

This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.

Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.


</pre>

* ⚠ **WARN** OS/2 VendorID value '    ' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---

A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.

The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.

Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;


Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.

When in doubt, please choose OFL for new font projects.


</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=1, enc=0, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---

A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.

The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).

The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;


Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.

When in doubt, please choose OFL for new font projects.


</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=1, enc=0, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=1, enc=0, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=1, enc=0, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=1, enc=0, name=14] [code: http-in-license-info]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is the Grid-fitting and Scan-conversion Procedure ('gasp') table set to optimize rendering?</summary>

* [com.google.fonts/check/gasp](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/gasp)
<pre>--- Rationale ---

Traditionally version 0 &#x27;gasp&#x27; tables were set so that font sizes below 8 ppem
had no grid fitting but did have antialiasing. From 9-16 ppem, just grid
fitting. And fonts above 17ppem had both antialiasing and grid fitting toggled
on. The use of accelerated graphics cards and higher resolution screens make
this approach obsolete. Microsoft&#x27;s DirectWrite pushed this even further with
much improved rendering built into the OS and apps.

In this scenario it makes sense to simply toggle all 4 flags ON for all font
sizes.


</pre>

* ⚠ **WARN** The gasp range 0xFFFF value 0x02 should be set to 0x0F. [code: unset-flags]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---

Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will
only differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.

However, a quotedbl should have 2 contours, unless the font belongs to a
display family.

This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.


</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: dollar	Contours detected: 2	Expected: 1 or 3
Glyph name: asterisk	Contours detected: 3	Expected: 1 or 4
Glyph name: I	Contours detected: 3	Expected: 1
Glyph name: J	Contours detected: 2	Expected: 1
Glyph name: K	Contours detected: 3	Expected: 1 or 2
Glyph name: L	Contours detected: 2	Expected: 1
Glyph name: T	Contours detected: 2	Expected: 1
Glyph name: V	Contours detected: 3	Expected: 1
Glyph name: X	Contours detected: 2	Expected: 1
Glyph name: b	Contours detected: 3	Expected: 2
Glyph name: f	Contours detected: 2	Expected: 1
Glyph name: h	Contours detected: 2	Expected: 1
Glyph name: k	Contours detected: 3	Expected: 1 or 2
Glyph name: l	Contours detected: 2	Expected: 1
Glyph name: m	Contours detected: 2	Expected: 1
Glyph name: n	Contours detected: 2	Expected: 1
Glyph name: p	Contours detected: 3	Expected: 2
Glyph name: q	Contours detected: 4	Expected: 2
Glyph name: t	Contours detected: 2	Expected: 1
Glyph name: u	Contours detected: 2	Expected: 1
Glyph name: v	Contours detected: 3	Expected: 1
Glyph name: x	Contours detected: 2	Expected: 1
Glyph name: yen	Contours detected: 3	Expected: 1 or 2
Glyph name: Igrave	Contours detected: 4	Expected: 2
Glyph name: Iacute	Contours detected: 4	Expected: 2
Glyph name: Icircumflex	Contours detected: 4	Expected: 2
Glyph name: Idieresis	Contours detected: 5	Expected: 3
Glyph name: Eth	Contours detected: 3	Expected: 2
Glyph name: ntilde	Contours detected: 3	Expected: 2
Glyph name: ugrave	Contours detected: 3	Expected: 2
Glyph name: uacute	Contours detected: 3	Expected: 2
Glyph name: ucircumflex	Contours detected: 3	Expected: 2
Glyph name: udieresis	Contours detected: 4	Expected: 3
Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: Dcroat	Contours detected: 3	Expected: 2
Glyph name: dcroat	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: hcircumflex	Contours detected: 3	Expected: 2
Glyph name: Itilde	Contours detected: 4	Expected: 2
Glyph name: Imacron	Contours detected: 4	Expected: 2
Glyph name: Ibreve	Contours detected: 4	Expected: 2
Glyph name: Iogonek	Contours detected: 4	Expected: 1 or 2
Glyph name: iogonek	Contours detected: 4	Expected: 2 or 3
Glyph name: Idotaccent	Contours detected: 4	Expected: 2
Glyph name: IJ	Contours detected: 5	Expected: 1 or 2
Glyph name: Jcircumflex	Contours detected: 3	Expected: 2
Glyph name: jcircumflex	Contours detected: 3	Expected: 2
Glyph name: uni0136	Contours detected: 4	Expected: 2 or 3
Glyph name: uni0137	Contours detected: 4	Expected: 2 or 3
Glyph name: Lacute	Contours detected: 3	Expected: 2
Glyph name: lacute	Contours detected: 3	Expected: 2
Glyph name: uni013B	Contours detected: 3	Expected: 2
Glyph name: uni013C	Contours detected: 3	Expected: 2
Glyph name: Lcaron	Contours detected: 3	Expected: 2
Glyph name: lcaron	Contours detected: 3	Expected: 2
Glyph name: Ldot	Contours detected: 3	Expected: 2
Glyph name: ldot	Contours detected: 3	Expected: 2
Glyph name: nacute	Contours detected: 3	Expected: 2
Glyph name: uni0146	Contours detected: 3	Expected: 2
Glyph name: ncaron	Contours detected: 3	Expected: 2
Glyph name: uni0162	Contours detected: 3	Expected: 1 or 2
Glyph name: uni0163	Contours detected: 3	Expected: 1 or 2
Glyph name: Tcaron	Contours detected: 3	Expected: 2
Glyph name: tcaron	Contours detected: 3	Expected: 2
Glyph name: umacron	Contours detected: 3	Expected: 2
Glyph name: ubreve	Contours detected: 3	Expected: 2
Glyph name: uring	Contours detected: 4	Expected: 3
Glyph name: uhungarumlaut	Contours detected: 4	Expected: 3
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: uogonek	Contours detected: 3	Expected: 1
Glyph name: uni01C7	Contours detected: 4	Expected: 2
Glyph name: uni01C8	Contours detected: 4	Expected: 3
Glyph name: uni01CA	Contours detected: 3	Expected: 2
Glyph name: uni01F5	Contours detected: 4	Expected: 3
Glyph name: uni0208	Contours detected: 5	Expected: 3
Glyph name: uni020A	Contours detected: 4	Expected: 2
Glyph name: uni021A	Contours detected: 3	Expected: 2
Glyph name: uni021B	Contours detected: 3	Expected: 2
Glyph name: uni03C0	Contours detected: 2	Expected: 1
Glyph name: uni0964	Contours detected: 2	Expected: 1
Glyph name: uni0965	Contours detected: 4	Expected: 2
Glyph name: trademark	Contours detected: 3	Expected: 2
Glyph name: uni25CC	Contours detected: 30	Expected: 16 or 12
Glyph name: uniFB00	Contours detected: 4	Expected: 1 or 2
Glyph name: Dcroat	Contours detected: 3	Expected: 2
Glyph name: Eth	Contours detected: 3	Expected: 2
Glyph name: I	Contours detected: 3	Expected: 1
Glyph name: IJ	Contours detected: 5	Expected: 1 or 2
Glyph name: Iacute	Contours detected: 4	Expected: 2
Glyph name: Ibreve	Contours detected: 4	Expected: 2
Glyph name: Icircumflex	Contours detected: 4	Expected: 2
Glyph name: Idieresis	Contours detected: 5	Expected: 3
Glyph name: Idotaccent	Contours detected: 4	Expected: 2
Glyph name: Igrave	Contours detected: 4	Expected: 2
Glyph name: Imacron	Contours detected: 4	Expected: 2
Glyph name: Iogonek	Contours detected: 4	Expected: 1 or 2
Glyph name: Itilde	Contours detected: 4	Expected: 2
Glyph name: J	Contours detected: 2	Expected: 1
Glyph name: Jcircumflex	Contours detected: 3	Expected: 2
Glyph name: K	Contours detected: 3	Expected: 1 or 2
Glyph name: L	Contours detected: 2	Expected: 1
Glyph name: Lacute	Contours detected: 3	Expected: 2
Glyph name: Lcaron	Contours detected: 3	Expected: 2
Glyph name: Ldot	Contours detected: 3	Expected: 2
Glyph name: T	Contours detected: 2	Expected: 1
Glyph name: Tcaron	Contours detected: 3	Expected: 2
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: V	Contours detected: 3	Expected: 1
Glyph name: X	Contours detected: 2	Expected: 1
Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: asterisk	Contours detected: 3	Expected: 1 or 4
Glyph name: b	Contours detected: 3	Expected: 2
Glyph name: dcroat	Contours detected: 3	Expected: 2
Glyph name: dollar	Contours detected: 2	Expected: 1 or 3
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: f	Contours detected: 2	Expected: 1
Glyph name: fi	Contours detected: 1	Expected: 3
Glyph name: fl	Contours detected: 1	Expected: 2
Glyph name: h	Contours detected: 2	Expected: 1
Glyph name: hcircumflex	Contours detected: 3	Expected: 2
Glyph name: iogonek	Contours detected: 4	Expected: 2 or 3
Glyph name: jcircumflex	Contours detected: 3	Expected: 2
Glyph name: k	Contours detected: 3	Expected: 1 or 2
Glyph name: l	Contours detected: 2	Expected: 1
Glyph name: lacute	Contours detected: 3	Expected: 2
Glyph name: lcaron	Contours detected: 3	Expected: 2
Glyph name: ldot	Contours detected: 3	Expected: 2
Glyph name: m	Contours detected: 2	Expected: 1
Glyph name: n	Contours detected: 2	Expected: 1
Glyph name: nacute	Contours detected: 3	Expected: 2
Glyph name: ncaron	Contours detected: 3	Expected: 2
Glyph name: ntilde	Contours detected: 3	Expected: 2
Glyph name: p	Contours detected: 3	Expected: 2
Glyph name: q	Contours detected: 4	Expected: 2
Glyph name: t	Contours detected: 2	Expected: 1
Glyph name: tcaron	Contours detected: 3	Expected: 2
Glyph name: trademark	Contours detected: 3	Expected: 2
Glyph name: u	Contours detected: 2	Expected: 1
Glyph name: uacute	Contours detected: 3	Expected: 2
Glyph name: ubreve	Contours detected: 3	Expected: 2
Glyph name: ucircumflex	Contours detected: 3	Expected: 2
Glyph name: udieresis	Contours detected: 4	Expected: 3
Glyph name: ugrave	Contours detected: 3	Expected: 2
Glyph name: uhungarumlaut	Contours detected: 4	Expected: 3
Glyph name: umacron	Contours detected: 3	Expected: 2
Glyph name: uni0136	Contours detected: 4	Expected: 2 or 3
Glyph name: uni0137	Contours detected: 4	Expected: 2 or 3
Glyph name: uni013B	Contours detected: 3	Expected: 2
Glyph name: uni013C	Contours detected: 3	Expected: 2
Glyph name: uni0146	Contours detected: 3	Expected: 2
Glyph name: uni0162	Contours detected: 3	Expected: 1 or 2
Glyph name: uni0163	Contours detected: 3	Expected: 1 or 2
Glyph name: uni01C7	Contours detected: 4	Expected: 2
Glyph name: uni01C8	Contours detected: 4	Expected: 3
Glyph name: uni01CA	Contours detected: 3	Expected: 2
Glyph name: uni021A	Contours detected: 3	Expected: 2
Glyph name: uni021B	Contours detected: 3	Expected: 2
Glyph name: uni0964	Contours detected: 2	Expected: 1
Glyph name: uni0965	Contours detected: 4	Expected: 2
Glyph name: uni25CC	Contours detected: 30	Expected: 16 or 12
Glyph name: uogonek	Contours detected: 3	Expected: 1
Glyph name: uring	Contours detected: 4	Expected: 3
Glyph name: v	Contours detected: 3	Expected: 1
Glyph name: x	Contours detected: 2	Expected: 1
Glyph name: yen	Contours detected: 3	Expected: 1 or 2 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Font contains .notdef as first glyph?</summary>

* [com.google.fonts/check/mandatory_glyphs](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/mandatory_glyphs)
<pre>--- Rationale ---

The OpenType specification v1.8.2 recommends that the first glyph is the
.notdef glyph without a codepoint assigned and with a drawing.

https://docs.microsoft.com/en-us/typography/opentype/spec
/recom#glyph-0-the-notdef-glyph

Pre-v1.8, it was recommended that a font should also contain a .null, CR and
space glyph. This might have been relevant for applications on MacOS 9.


</pre>

* ⚠ **WARN** Font should contain the .notdef glyph as the first glyph, it should not have a Unicode value assigned and should contain a drawing.

</details>
<details>
<summary>⚠ <b>WARN:</b> Check mark characters are in GDEF mark glyph class)</summary>

* [com.google.fonts/check/gdef_spacing_marks](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/gdef.html#com.google.fonts/check/gdef_spacing_marks)
<pre>--- Rationale ---

Glyphs in the GDEF mark glyph class should be non-spacing.
Spacing glyphs in the GDEF mark glyph class may have incorrect anchor
positioning that was only intended for building composite glyphs during design.


</pre>

* ⚠ **WARN** The following spacing glyphs may be in the GDEF mark glyph class by mistake:
	 tm_Anusvara [code: spacing-mark-glyphs]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check mark characters are in GDEF mark glyph class</summary>

* [com.google.fonts/check/gdef_mark_chars](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/gdef.html#com.google.fonts/check/gdef_mark_chars)
<pre>--- Rationale ---

Mark characters should be in the GDEF mark glyph class.


</pre>

* ⚠ **WARN** The following mark characters could be in the GDEF mark glyph class:
	 U+030F, U+0BBE, U+0BBF, U+0BC0, U+0BC1, U+0BC2, U+0BC6, U+0BC7, U+0BC8, U+0BCA, U+0BCB, U+0BCC and U+0BD7 [code: mark-chars]

</details>
<br>
</details>

### Summary

| 💔 ERROR | 🔥 FAIL | ⚠ WARN | 💤 SKIP | ℹ INFO | 🍞 PASS | 🔎 DEBUG |
|:-----:|:----:|:----:|:----:|:----:|:----:|:----:|
| 0 | 10 | 8 | 85 | 6 | 72 | 0 |
| 0% | 6% | 4% | 47% | 3% | 40% | 0% |

**Note:** The following loglevels were omitted in this report:
* **SKIP**
* **INFO**
* **PASS**
* **DEBUG**
