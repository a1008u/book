all:
	make makedir;
	make split;
	make html;
	make html_link;

makedir:
	csplit /workspaces/book/src/book_1/main.md '/^## .*/' {5};\
	for i in $$(seq 1 $$(($$(ls -1 x*| wc -l)-1)) ); do\
		rm -rf /workspaces/book/src/book_1/$$i;\
		mkdir -p /workspaces/book/src/book_1/$$i;\
		mkdir /workspaces/book/src/book_1/$$i/$$i$$1_link;\
		mv /workspaces/book/src/book_1/xx0$$i /workspaces/book/src/book_1/$$i/$$i.md;\
		rm -rf /workspaces/book/src/book_1/xx00;\
	done

split:
	@for i in $$(seq 1 $$(($$(ls -I Makefile -I main.md -1| wc -l))) ); do\
		csplit /workspaces/book/src/book_1/$$i/$$i.md '/^### .*/' {$$(($$(grep -o -i '^### ' /workspaces/book/src/book_1/$$i/$$i.md| wc -l)-1))};\
		for ix in $$(seq 1 $$(($$(ls -1 x*| wc -l)-1)) ); do\
			mv /workspaces/book/src/book_1/xx0$$ix /workspaces/book/src/book_1/$$i/$$i$$1_link/$$ix.md;\
		done;\
	done
	rm -rf /workspaces/book/src/book_1/xx00;

html:
	rm -rf /workspaces/book/docs/book_1
	mkdir -p /workspaces/book/docs/book_1
	@for i in $$(seq 1 $$(($$(ls -I Makefile -I main.md -1| wc -l))) ); do\
		mkdir -p /workspaces/book/docs/book_1/$$i;\
		for c in $$(seq 1 $$(ls -1 /workspaces/book/src/book_1/$$i| wc -l) ); do\
			npx markmap-cli -o /workspaces/book/docs/book_1/$$i/$$i.html /workspaces/book/src/book_1/$$i/$$i.md;\
		done;\
		mkdir -p /workspaces/book/docs/book_1/$$i/$$i$$1_link;\
		for c in $$(seq 1 $$(ls -1 /workspaces/book/src/book_1/$$i/$$i$$1_link| wc -l) ); do\
			npx markmap-cli -o /workspaces/book/docs/book_1/$$i/$$i$$1_link/$$c.html /workspaces/book/src/book_1/$$i/$$i$$1_link/$$c.md;\
		done;\
	done

html_link:
	npx markmap-cli -o /workspaces/book/docs/book_1/main_link.html /workspaces/book/src/book_1/main_link.md;
