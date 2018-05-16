# Effects Eighty

This font family is designed to duplicate as closely as possible
the output from the venerable Epson FX-80 dot matrix printer.

I grew up using this printer, and so its scraggly output has
a sentimental value for me.

My aim is to create these fonts by creating a Python script which will
use the python-fontforge package.  This library has all the power of
the fontforge GUI application, but in the form of a python extension.

This typeface was developed on an Ubuntu Linux 12.04 LTS system, and so
it uses the version of the python-fontforge package that the 12.04 LTS
release provides.  If you use other versions, your mileage may vary.

The FX-80 can do a fairly large range of different print styles (what Epson
called "elite", "pica", "emphasized", "compressed", etc.,) as well as
the versions using the italic bitmaps.  I have elected to use only the
"normal" forms, using the 12x10 matrix as illustrated in the Epson
manuals.  The bitmaps are nominally formed on a 6x10 grid, but the
characters actually use horizontal positioning on 12 "half-dot"
positions.

I have defined these bitmaps as a dictionary of strings, where one line
of each string defines one row in the bitmap.  An asterisk ('*') indicates
that a dot is to be drawn at that point.  Any other character will be ignored.
I use periods to define the non-drawing positions.

The script takes the positions of these asterisks within the bitmap string
and converts them to PostScript instructions, which it writes into an EPS
file, one per glyph.  It then tells the fontforge module to import this
EPS file in order to obtain the contours for the glyph in the font.  After
all the glyphs have been imported in this way, and various tweaks applied,
such as overlap removal, coordinate rounding, and correction of contour
direction, the fonts are written out to the final font files.

## Update: v1.1, Aug. 5th, 2017

I have exported the FontForge `.sfd` files to UFO, and from there to
Glyphs files.  Using Glyphs, I have remade the various font files in
hopefully better form, and also added .woff and .woff2 files for use
on websites.  There is also a handy CSS file to use with the woff2 files.

## Enjoy!

Peter H.

