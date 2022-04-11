SHELL = /bin/bash
bin_PROGRAMS = subb
subb_SOURCES = subb.c
STAG=`bash ./bump-tag`

package:
	sudo checkinstall --install=no --pkgname $(bin_PROGRAMS)

stag:
	echo "##### stag: $(STAG)"
	git tag -a "$(STAG)" -m "version upgrade to $(STAG)"

stagpush:
	git push --tags
