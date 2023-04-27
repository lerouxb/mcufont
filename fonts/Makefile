# Path to the command-line utility program
MCUFONT = ../encoder/mcufont

# Names of fonts to process
#FONTS = Manrope-SemiBold24 Manrope-SemiBold32 ChivoMono-Medium24 ChivoMono-Medium32 DSEG14Classic-Bold64
FONTS = Manrope-SemiBold16 Manrope-SemiBold24 Manrope-SemiBold32 DSEG14Classic-Bold20 DSEG14Classic-Bold40 DSEG14Classic-Bold64


# Characters to include in the fonts
#CHARS = 0-255 0x2010-0x2015
CHARS = 0-127 0x2022

all: $(FONTS:=.c) $(FONTS:=.dat) fonts.h

clean:
	rm -f $(FONTS:=.c) $(FONTS:=.dat)

fonts.h: $(FONTS:=.c)
	/bin/echo -e $(foreach font,$(FONTS),'\n#include "'$(font)'.c"') > $@

%.c: %.dat $(MCUFONT)
	$(MCUFONT) rlefont_export $<

Manrope-SemiBold16.dat: Manrope-SemiBold.ttf
	$(MCUFONT) import_ttf $< 16
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50
	
Manrope-SemiBold24.dat: Manrope-SemiBold.ttf
	$(MCUFONT) import_ttf $< 24
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50

Manrope-SemiBold32.dat: Manrope-SemiBold.ttf
	$(MCUFONT) import_ttf $< 32
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50

#ChivoMono-Medium24.dat: ChivoMono-Medium.ttf
#	$(MCUFONT) import_ttf $< 24
#	$(MCUFONT) filter $@ $(CHARS)
#	$(MCUFONT) rlefont_optimize $@ 50

#ChivoMono-Medium32.dat: ChivoMono-Medium.ttf
#	$(MCUFONT) import_ttf $< 32
#	$(MCUFONT) filter $@ $(CHARS)
#	$(MCUFONT) rlefont_optimize $@ 50
#
DSEG14Classic-Bold20.dat: DSEG14Classic-Bold.ttf
	$(MCUFONT) import_ttf $< 20
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50

DSEG14Classic-Bold40.dat: DSEG14Classic-Bold.ttf
	$(MCUFONT) import_ttf $< 40
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50

DSEG14Classic-Bold64.dat: DSEG14Classic-Bold.ttf
	$(MCUFONT) import_ttf $< 64
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50
