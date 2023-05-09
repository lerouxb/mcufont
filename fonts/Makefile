# Path to the command-line utility program
MCUFONT = ../encoder/mcufont

# Names of fonts to process
#FONTS = Manrope-SemiBold24 Manrope-SemiBold32 ChivoMono-Medium24 ChivoMono-Medium32 DSEG14Classic-Bold64
FONTS = Manrope-SemiBold16 Manrope-SemiBold24 Manrope-SemiBold32 \
        DSEG7Classic-Bold16 DSEG7Classic-Bold24 DSEG7Classic-Bold48 \
        MaterialIcons-Regular16

# Characters to include in the fonts
#CHARS = 0-255 0x2010-0x2015
CHARS = 0-127 0x2022 0xe1a4 0xe1a3 0xebd4 0xebe2 0xebd2 0xebdd 0xebd9 0xebe0

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

DSEG7Classic-Bold16.dat: DSEG7Classic-Bold.ttf
	$(MCUFONT) import_ttf $< 16
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50

DSEG7Classic-Bold24.dat: DSEG7Classic-Bold.ttf
	$(MCUFONT) import_ttf $< 24
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50

DSEG7Classic-Bold48.dat: DSEG7Classic-Bold.ttf
	$(MCUFONT) import_ttf $< 48
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50

MaterialIcons-Regular16.dat: MaterialIcons-Regular.ttf
	$(MCUFONT) import_ttf $< 16
	$(MCUFONT) filter $@ $(CHARS)
	$(MCUFONT) rlefont_optimize $@ 50

