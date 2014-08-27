STRATEGO_TBL = /usr/local/packages/strategoxt-0.17/stratego-front/syn/StrategoStratego.tbl

SDF_FILES =  EnglishLex.sdf       \
             English.sdf

%.tbl : %
	sdf2table -i $< -o $@

all : English.tbl English.str

English.def : English.sdf EnglishLex.sdf
	pack-sdf -i $< -o $@

English.tbl : English.def
	sdf2table -i $< -o $@ -m English

English.rtg : English.def English.tbl
	sdf2rtg -i English.def -m English -o English.rtg

English.str : English.rtg
	rtg2sig -i English.rtg -o English.str

clean :
	rm -f *.def *.tbl English.sig
