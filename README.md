## DCRAW

Imported form [Dave Coffin's](http://www.cybercom.net/~dcoffin/) web page [Decoding raw digital photos in Linux](http://www.cybercom.net/~dcoffin/dcraw/)


 Note to Linux distributors: The only executable files that should be installed by a dcraw package are "dcraw", "clean_crw", and maybe "fuji_green", "fujiturn", and "fujiturn16". My shell scripts are dangerous and should only be installed in a "doc" directory without execute permission.

* dcraw.c -- decodes raw photos, extracts thumbnails, and displays metadata

   Supports 688 cameras at last count. Compile with "gcc -o dcraw -O4 dcraw.c -lm -ljasper -ljpeg -llcms2" or "gcc -o dcraw -O4 dcraw.c -lm -DNODEPS". Run with no arguments to see a usage message. Don't complain that 16-bit output is too dark -- read the FAQ!
* UNIX manpage for dcraw

    This is dcraw's official user documentation, updated in lockstep with the source code.
* rawphoto.c -- basic plugin for GIMP 1.2 & 2.0

    After installing "dcraw", do "gimptool --install rawphoto.c". My plugin provides a simple dialog box for loading raw files into the Gimp. Udi Fuchs and Joseph Heled have written much nicer plugins, with live preview, histograms, and color curves.
* .badpixels -- my camera's "hot pixels"

    This file tells dcraw which pixels have died and when, so that it can interpolate around them.
* dcraw.c,v -- complete unabridged RCS file

    This file contains the entire history of dcraw.c since its conception on February 23, 1997. If you don't have the RCS toolkit, download it here.
* parse.c -- read image data structures

    This program displays CIFF and TIFF data structures in a very cryptic format.
* clean_crw.c -- clean Canon CRW files

    Recovered or undeleted CRW files often have junk appended to them that makes them unreadable. This program safely cleans CRW files.
* fujiturn.c -- rotate Fuji Super CCD images

    An alternative to dcraw's built-in Fuji rotation.
* fuji_green.c -- convert Fuji green pixels to PGM
 
    A side benefit of the Fuji Super CCD design is that its green pixels make nice greyscale images. 

For hackers only:

* decompress.c is a simple reference decompressor for CRW files.
* sony_clear.c decrypts SRF files from the Sony DSC-F828. 
