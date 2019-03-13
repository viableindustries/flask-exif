# Python EXIF parsing

**pexif** is a Python library for  parsing and more importantly
editing EXIF data in JPEG files.

This grew out of a need to add GPS tagged data to my images,
Unfortunately the other libraries out there couldn't do updates and
didn't seem easily architectured to be able to add such a thing. Ain't
reusable software grand!

## Apps

- **dump_exif.py**: Output the EXIF file from a given file.
- **setgps.py**: Set the GPS metadata on a file.
- **getgps.py**: Get the GPS metadata from a file.
- **noop.py**: This is a no-op on a jpeg file. Useful for testing images are preserved across 
operations using pexif. Note that the binary data will not be exact as pexif will compress 
unused space in the file, however running it on a file twice should end up with the same data.

## Examples

- **hello.py**: Add a simple description to a photo.

## Status:

**WARNING**: This could destroy your images!! Backup your images before using.

Currently it parses files from my Canon without a problem, and is able to
add a GPS tag without corrupting the rest of the image.

## References

This work couldn't be done with the reference for the spec. In particular I worked to:

- http://www.exiv2.org/Exif2-2.PDF

For the format of the Canon stuff I used:

- http://www.burren.cx/david/canon.html

For the format of FujiFILM make note:

- http://www.ozhiker.com/electronics/pjmt/jpeg_info/fujifilm_mn.html

## Acknowledgments:
 
[Nick Carter](nick.carter@roke.co.uk) provided conker.jpg which is used for testing FUJIFILM exif data.

[Nick Burch](nick@gagravarr.org) provided noexif.jpg which is used
for testing inputs that don't have an existing EXIF segment. Nick burch
also found an error in GeoTags on the S60.

[Christopher Jones](short.jones.cipher@gmail.com) who inspired updating
my examples to show how copying EXIF data from one jpeg to another.

[Roland Klabunde](roland.klabunde@freenet.de) who also found a bug in
 the GeoTag functionality.

[Marcell Lengyel](miketkf@gmail.com) for adding better support for
 Canon g3 and FujiFilm z5fd.

[Andrew Baumann](http://ab.id.au/) for finding a bug in dealing with
 extended IFD sections, and supplying the timezone adjustment script.
