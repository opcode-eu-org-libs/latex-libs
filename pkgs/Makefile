all: ehhline.tgz labels4easylist.tgz pdfArticle.tgz vtable.tgz

clean:
	rm -fr build-tempdir *.tgz

../docs/%.pdf: ../docs/%.tex
	(cd ../docs; make $@)

%.tgz: ../docs/%.pdf ../docs/%.txt ../docs/%.tex
	rm -f $@
	mkdir -p build-tempdir/$(basename $@)
	cp ../docs/$(basename $@).pdf  build-tempdir/$(basename $@)/
	cp ../docs/$(basename $@).tex  build-tempdir/$(basename $@)/
	cp ../docs/$(basename $@).txt  build-tempdir/$(basename $@)/README
	cp $(basename $@).*            build-tempdir/$(basename $@)/
	(cd build-tempdir; tar -czf ../$@  $(basename $@))
