all: ehhline.pdf labels4easylist.pdf pdfArticle.pdf vtable.pdf

clean:
	rm -fr build-tempdir *.pdf

prepare:
	mkdir -p build-tempdir
	(cd build-tempdir; ln -fs ../../pkgs/* .)

%.pdf: %.tex | prepare
	(cd build-tempdir; ln -fs ../$< .; lualatex $< && lualatex $<)
	mv build-tempdir/$@ .
