XSL_DTDDIR= /usr/share/sgml/docbook/xml-dtd-4.1.2-1.0-48.fc12
XSLTPROC_OPTS=	\
	--stringparam chunk.first.sections 1 \
	--stringparam use.id.as.filename 1 \
	--stringparam section.autolabel 1 \
	--path $(XSL_DTDDIR)
XSL_STYLESHEET= /usr/share/sgml/docbook/xsl-stylesheets/html/chunk.xsl

all:	HOWTO/index.html mini-HOWTO/index.html

HOWTO mini-HOWTO:
	@mkdir -p $@

HOWTO/index.html:	LVS-HOWTO.xml HOWTO
	@O=`dirname $@`; xsltproc $(XSLTPROC_OPTS) -o $$O/ $(XSL_STYLESHEET) $<;
	
mini-HOWTO/index.html:	LVS-mini-HOWTO.xml mini-HOWTO
	@O=`dirname $@`; xsltproc $(XSLTPROC_OPTS) -o $$O/ $(XSL_STYLESHEET) $<;
