dist_man1_MANS=	shell.man mjoin.man
dist_doc_DATA=	shell.txt mjoin.txt

EXTRA_DIST=	shell.mdoc mjoin.mdoc
DISTCLEANFILES=	$(dist_man1_MANS) $(dist_doc_DATA)

if BUILD_MANUALS

SUFFIXES=	.mdoc .man .txt

.mdoc.man:
	$(MANDOC) -T man -I os=Unix $< >$@

.mdoc.txt:
	$(MANDOC) -T ascii -I os=Unix $< | $(COL) -b >$@

else

$(dist_man1_MANS) $(dist_doc_DATA):
	@echo 'You lack the required utilities. Can not rebuild manuals' >&2
	@exit 1

endif	# BUILD_MANUALS
