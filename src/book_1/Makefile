1_chapter = 1
2_chapter = 2
3_chapter = 3
4_chapter = 4
5_chapter = 5
6_chapter = 6

01=01
02=02
03=03
04=04
05=05
06=06
07=07
08=08
09=09

all:
	make makedir;
	make split;

makedir:
	csplit /workspaces/book/src/book_1/main.md '/^## .*/' {5};
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
	npx markmap-cli -o /workspaces/book/docs/book_1/fp_mind_link.html /workspaces/book/src/book_1/fp_mind_link.md;
	------------------------------------
	npx markmap-cli -o /workspaces/book/docs/book_1/$(1_chapter).html /workspaces/book/src/book_1/$(1_chapter)/$(1_chapter).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/$(1_chapter)_link.html /workspaces/book/src/book_1/$(1_chapter)/$(1_chapter)_link.md;
	npx markmap-cli -o /workspaces/book/docs/book_1/1_link/$(01).html /workspaces/book/src/book_1/$(1_chapter)/1_link/$(01).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/1_link/$(02).html /workspaces/book/src/book_1/$(1_chapter)/1_link/$(02).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/1_link/$(03).html /workspaces/book/src/book_1/$(1_chapter)/1_link/$(03).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/1_link/$(04).html /workspaces/book/src/book_1/$(1_chapter)/1_link/$(04).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/1_link/$(05).html /workspaces/book/src/book_1/$(1_chapter)/1_link/$(05).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/1_link/$(06).html /workspaces/book/src/book_1/$(1_chapter)/1_link/$(06).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/1_link/$(07).html /workspaces/book/src/book_1/$(1_chapter)/1_link/$(07).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/1_link/$(08).html /workspaces/book/src/book_1/$(1_chapter)/1_link/$(08).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/1_link/$(09).html /workspaces/book/src/book_1/$(1_chapter)/1_link/$(09).md;
	----
	npx markmap-cli -o /workspaces/book/docs/book_1/$(2_chapter).html /workspaces/book/src/book_1/$(2_chapter)/$(2_chapter).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/$(2_chapter)_link.html /workspaces/book/src/book_1/$(2_chapter)/$(2_chapter)_link.md;
	npx markmap-cli -o /workspaces/book/docs/book_1/2_link/$(01).html /workspaces/book/src/book_1/$(2_chapter)/2_link/$(01).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/2_link/$(02).html /workspaces/book/src/book_1/$(2_chapter)/2_link/$(02).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/2_link/$(03).html /workspaces/book/src/book_1/$(2_chapter)/2_link/$(03).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/2_link/$(04).html /workspaces/book/src/book_1/$(2_chapter)/2_link/$(04).md;
	----
	npx markmap-cli -o /workspaces/book/docs/book_1/$(3_chapter).html /workspaces/book/src/book_1/$(3_chapter)/$(3_chapter).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/$(3_chapter)_link.html /workspaces/book/src/book_1/$(3_chapter)/$(3_chapter)_link.md;
	npx markmap-cli -o /workspaces/book/docs/book_1/3_link/$(01).html /workspaces/book/src/book_1/$(3_chapter)/3_link/$(01).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/3_link/$(02).html /workspaces/book/src/book_1/$(3_chapter)/3_link/$(02).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/3_link/$(03).html /workspaces/book/src/book_1/$(3_chapter)/3_link/$(03).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/3_link/$(04).html /workspaces/book/src/book_1/$(3_chapter)/3_link/$(04).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/3_link/$(05).html /workspaces/book/src/book_1/$(3_chapter)/3_link/$(05).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/3_link/$(06).html /workspaces/book/src/book_1/$(3_chapter)/3_link/$(06).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/3_link/$(07).html /workspaces/book/src/book_1/$(3_chapter)/3_link/$(07).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/3_link/$(08).html /workspaces/book/src/book_1/$(3_chapter)/3_link/$(08).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/3_link/$(09).html /workspaces/book/src/book_1/$(3_chapter)/3_link/$(09).md;
	----
	npx markmap-cli -o /workspaces/book/docs/book_1/$(4_chapter).html /workspaces/book/src/book_1/$(4_chapter)/$(4_chapter).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/$(4_chapter)_link.html /workspaces/book/src/book_1/$(4_chapter)/$(4_chapter)_link.md;
	npx markmap-cli -o /workspaces/book/docs/book_1/4_link/$(01).html /workspaces/book/src/book_1/$(4_chapter)/4_link/$(01).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/4_link/$(02).html /workspaces/book/src/book_1/$(4_chapter)/4_link/$(02).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/4_link/$(03).html /workspaces/book/src/book_1/$(4_chapter)/4_link/$(03).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/4_link/$(04).html /workspaces/book/src/book_1/$(4_chapter)/4_link/$(04).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/4_link/$(05).html /workspaces/book/src/book_1/$(4_chapter)/4_link/$(05).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/4_link/$(06).html /workspaces/book/src/book_1/$(4_chapter)/4_link/$(06).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/4_link/$(07).html /workspaces/book/src/book_1/$(4_chapter)/4_link/$(07).md;
	----
	npx markmap-cli -o /workspaces/book/docs/book_1/$(5_chapter).html /workspaces/book/src/book_1/$(5_chapter)/$(5_chapter).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/$(5_chapter)_link.html /workspaces/book/src/book_1/$(5_chapter)/$(5_chapter)_link.md;
	npx markmap-cli -o /workspaces/book/docs/book_1/5_link/$(01).html /workspaces/book/src/book_1/$(5_chapter)/5_link/$(01).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/5_link/$(02).html /workspaces/book/src/book_1/$(5_chapter)/5_link/$(02).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/5_link/$(03).html /workspaces/book/src/book_1/$(5_chapter)/5_link/$(03).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/5_link/$(04).html /workspaces/book/src/book_1/$(5_chapter)/5_link/$(04).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/5_link/$(05).html /workspaces/book/src/book_1/$(5_chapter)/5_link/$(05).md;
	----
	npx markmap-cli -o /workspaces/book/docs/book_1/$(6_chapter).html /workspaces/book/src/book_1/$(6_chapter)/$(6_chapter).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/$(6_chapter)_link.html /workspaces/book/src/book_1/$(6_chapter)/$(6_chapter)_link.md;
	npx markmap-cli -o /workspaces/book/docs/book_1/6_link/$(01).html /workspaces/book/src/book_1/$(6_chapter)/6_link/$(01).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/6_link/$(02).html /workspaces/book/src/book_1/$(6_chapter)/6_link/$(02).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/6_link/$(03).html /workspaces/book/src/book_1/$(6_chapter)/6_link/$(03).md;
	npx markmap-cli -o /workspaces/book/docs/book_1/6_link/$(04).html /workspaces/book/src/book_1/$(6_chapter)/6_link/$(04).md;
