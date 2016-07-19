# Info used in building the MAN files
man_MANS = cfengine.8 cfagent.8  cfenvd.8  cfenvgraph.8  cfexecd.8  cfkey.8  cfrun.8  cfservd.8 cfshow.8 cfetoolcheck.8   cfetooldump.8   cfetoolimport.8  cfetoolupdate.8 cfetoolcreate.8  cfetoolgraph.8  cfetoolinfo.8  cfetool.8  cfdoc.8

# Info used in building the Info files
info_TEXINFOS = cfengine-Reference.texinfo cfengine-Tutorial.texinfo
infofiles = $(info_TEXINFOS:.texinfo=.info)
MAKEINFOHTML = $(MAKEINFO) --html --no-split

# Info used in building and installing HTML files
htmlfiles = $(info_TEXINFOS:.texinfo=.html)

htmldir = $(pkgdatadir)/html
html_DATA = $(htmlfiles)

# Make sure these get distributed with everything else.

EXTRA_DIST = cfagent.8 cfenvd.8 cfenvgraph.8 cfexecd.8 cfkey.8 cfrun.8 cfservd.8 cfengine.8 cfshow.8 cfetoolcheck.8   cfetooldump.8   cfetoolimport.8  cfetoolupdate.8 cfetoolcreate.8  cfetoolgraph.8  cfetoolinfo.8 cfetoolcheck.8   cfetooldump.8   cfetoolimport.8  cfetoolupdate.8 cfetoolcreate.8  cfetoolgraph.8  cfetoolinfo.8 texinfo.tex $(htmlfiles) $(infofiles)

SUFFIXES = html

%.html : %.texinfo
	${MAKEINFO} -I $(srcdir) --html --no-split $<

#
# Some basic clean ups
#
MOSTLYCLEANFILES = *~ *.orig

#
# Get everything removed down to where rebuilding requires:
# "make; make install"
# 
CLEANFILES = $(htmlfiles) $(psfiles) $(pdffiles)

#
# Get everything removed down to where rebuilding requires:
# "configure; make; make install"
#
DISTCLEANFILES = *.log *.aux *.mbs *.mb *.info*

#
# Get everything removed down to where rebuilding requires:
# "aclocal; autoconf; autoheader; automake --add-missing"
# "configure; make; make install"
#
MAINTAINERCLEANFILES = Makefile.in mdate-sh
