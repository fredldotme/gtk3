include $(top_srcdir)/Makefile.decl

if HAVE_INTROSPECTION
GENERATED_ITEMS = \
	introspection.body.mak	\
	Gdk_3_0_gir_list		\
	GdkWin32_3_0_gir_list	\
	Gtk_3_0_gir_list

MSVC_INTROSPECTION_INTERMEDIATE_FILES = Gdk-3.0.gir.msvc.introspect GdkWin32-3.0.gir.msvc.introspect Gtk-3.0.gir.msvc.introspect

introspection.body.mak: $(MSVC_INTROSPECTION_INTERMEDIATE_FILES)
	-$(RM) introspection.body.mak
	for F in `ls *.msvc.introspect`; do \
		case $$F in \
			*)	cat $(top_builddir)/build/win32/$$F >>introspection.body.mak \
			;; \
		esac; \
	done
	$(RM) $(MSVC_INTROSPECTION_INTERMEDIATE_FILES)

DISTCLEANFILES = $(GENERATED_ITEMS)

else
GENERATED_ITEMS =
DISTCLEANFILES =
endif

SUBDIRS =	\
	vs9 	\
	vs10	\
	vs11	\
	vs12	\
	vs14	\
	vs15

EXTRA_DIST +=	\
	detectenv-msvc.mak		\
	introspection-msvc.mak		\
	gtk-introspection-msvc.mak	\
	replace.py			\
	pc_base.py			\
	gtkpc.py			\
	$(GENERATED_ITEMS)

-include $(top_srcdir)/git.mk
