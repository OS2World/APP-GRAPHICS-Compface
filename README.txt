Compface for OS/2 - 48x48x1 image compression and decompression
===============================================================

Compface is an image compression and decompression application,
it takes an 'icon' image format as input and generates a compressed
ascii string, and the other way around (ascii to icon format).

Compface is used to create X-Face: email headers. You can embed
these X-Faces in your emails and supported email clients will
be able to read the image and display it while the other user
is reading your email. It is widely used in newsgroups. I compiled
this port to add support for X-Face in my WebMail/2 application
which can be found at: http://www.michelinakis.gr/Dimitris.

The -X parameter forces compface/uncompface to use XBM image
format instead of 'icon' format.

It is strongly suggested you use the -X paramter for XBM image
format, because the 'icon' format is an old and unsupported format
and you'll have a very hard time finding applications to support it.

-- Dimitris 'sehh' Michelinakis
-- dimitris@michelinakis.gr
-- http://www.michelinakis.gr/Dimitris



This is the original Compface readme text:
==========================================

Compface - 48x48x1 image compression and decompression
Copyright (c) James Ashton 1990.
Written 89/11/11

Feel free to distribute this source at will so long as the above
message and this message are included in full.

[I have put MIT in the License field of the LSM descriptions since this
seems to capture the original author's intent most closely, bearing in
mind that he wrote this before the various free software licenses were
categorised. - Ken]

The programme (two programmes really - but they're just links to each
other) converts 48x48x1 images to and from a compressed format.  The
uncompressed images are expected to contain 48x48/4 (576) hex digits.
All other characters and any `0's followed by `X' or `x' are ignored.
Usually the files are 48 lines of "0x%04X,0x%04X,0x%04X,".  The
compressed images contain some number of printable characters.  Non
printable characters, including ` ' are ignored.  The purpose of the
programme is to allow the inclusion of face images within mail headers
using the field name `X-face: '.

The programmes make use of a library which can be used to allow the
compression and decompression algorithms to be used in other
programmes such as mail despatchers and mail notification daemons.

A small amount of editing in the Makefile may be required to get it
going - mainly setting EXECUTABLE to what you want and putting the
manual entry in the right place.

						James Ashton.
						jaa@cs.su.oz.au

1999-06-18

I have merged the -X patch by Piete Brooks <Piete.Brooks@cl.cam.ac.uk>
into the sources and amended the man page. I have given this the
version number 1.1 so that it can be submitted to freshmeat.net and
metalabs.unc.edu.

						Ken Yap
						ken@acm.org

2000-11-22

Added support for strerror().  Incremented version to 1.4
