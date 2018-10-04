# Fonttools
Fonttools to merge Digital Signature to TrueType font file
Fonttools version 2.4 merges a Digital Signature into a TrueType (.ttf) font file, 
but now this operation breaks the font with a serious error on Mac OS X 10.13.6.
So I downloaded the latest Fonttools v3.19.0 here...
 https://github.com/fonttools/fonttools
 
 Questions are:
 
 How to create the dsig_Fldr on the Desktop?
 
 What code routine to use to re-create this operation?
 
Here is the code +actions I always have used successfully on Mac OS X, but need a new routine to use with v3.19.0

Launch Terminal

cd Adrians-iMac:~ adrianshome$

PASTE:

FLDR="${HOME}/Desktop/Dsig fldr"
mkdir -p "$FLDR"
cd "$FLDR"
cat > dsig.ttx<<EOF
<?xml version="1.0" encoding="ISO-8859-1"?>
<ttFont sfntVersion="\x00\x01\x00\x00" ttLibVersion="2.4">
<DSIG>
<hexdata>
00000001 00000000
</hexdata>
</DSIG>
</ttFont>
EOF
open .

RETURN:

Adrians-iMac:~ adrianshome$ 

ENTER:

adddsig (followed by a space)

DRAG FONT FILE TO TERMINAL:

Adrians-iMac:Dsig fldr adrianshome$ adddsig /Users/adrianshome/Desktop/Dsig\ fldr/AdmarBolItaStd\ copy.ttf 

RETURN

Compiling "/Users/adrianshome/Desktop/Dsig fldr/AdmarBolItaStd.ttx" to "/Users/adrianshome/Desktop/Dsig fldr/AdmarBolItaStd.ttf"...
Parsing 'DSIG' table...

OVERWRITES ORIGINAL TTF FILE (check time difference):

Adrians-iMac:~ adrianshome$
