EXTRA_DIST =	setup.py \
		bin \
		suricata

if HAVE_PYTHON
all-local:
	cd $(srcdir) && \
		$(HAVE_PYTHON) setup.py build --build-base $(abs_builddir)

install-exec-local:
	cd $(srcdir) && \
		$(HAVE_PYTHON) setup.py build --build-base $(abs_builddir) \
		install --prefix $(DESTDIR)$(prefix)

uninstall-local:
	rm -f $(DESTDIR)$(bindir)/suricatactl
	rm -rf $(DESTDIR)$(prefix)/lib*/python*/site-packages/suricata
	rm -rf $(DESTDIR)$(prefix)/lib*/python*/site-packages/suricata-[0-9]*.egg-info

clean-local:
	cd $(srcdir) && \
		$(HAVE_PYTHON) setup.py clean \
		--build-base $(abs_builddir)
	rm -rf scripts-* lib* build
	find . -name \*.pyc -print0 | xargs -0 rm -f

distclean-local:
	rm -f version
endif
