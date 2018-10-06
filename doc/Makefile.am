dist_man1_MANS=	shell.man
dist_doc_DATA=	shell.txt
EXTRA_DIST=	shell.mdoc
DISTCLEANFILES=	shell.man shell.txt

if !BUILD_MANUALS

$(dist_man1_MANS) $(dist_doc_DATA):
	@echo 'You lack the required utilities. Can not rebuild manuals' >&2
	@exit 1

else

shell.man:	$(srcdir)/shell.mdoc
	$(MANDOC) -T man -I os=Unix $(srcdir)/shell.mdoc >shell.man || true

shell.txt:	$(srcdir)/shell.mdoc
	$(MANDOC) -T ascii -I os=Unix $(srcdir)/shell.mdoc | \
	$(COL) -b >shell.txt || true

endif	# BUILD_MANUALS
