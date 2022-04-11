SHELL = /bin/bash
bin_PROGRAMS = subb
subb_SOURCES = subb.c
STAG=`git describe|awk -F[-.] '{printf("%s-%d.%d.%d\n",$$1,$$2,$$3,$$4+1);}'`

package:
	sudo checkinstall --install=no --pkgname $(bin_PROGRAMS)

stag:
	echo "##### stag: $(STAG)"
	git tag -a "$(STAG)" -m "version upgrade to $(STAG)"
	echo "$(STAG)" > ./last-tag
	git add last-tag
	git commit -m "new last-tag value $(STAG)"
	git push

stagpush:
	git push --tags
