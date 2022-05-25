s_count=11
book=book_2

all:
	make makedir;
	make split;
	make html;
	make html_link;

makedir:
	csplit /workspaces/book/src/$(book)/main.md '/^## .*/' {$(s_count)};\
	for i in $$(seq 1 $$(($(s_count)+1)) ); do\
		rm -rf /workspaces/book/src/$(book)/$$i;\
		mkdir -p /workspaces/book/src/$(book)/$$i;\
		mkdir /workspaces/book/src/$(book)/$$i/$$i$$1_link;\
		if [ $$i -lt 10 ] ; then\
			mv /workspaces/book/src/$(book)/xx0$$i /workspaces/book/src/$(book)/$$i/$$i.md;\
		else\
			mv /workspaces/book/src/$(book)/xx$$i /workspaces/book/src/$(book)/$$i/$$i.md;\
		fi;\
		rm -rf /workspaces/book/src/$(book)/xx00;\
	done

split:
	@for i in $$(seq 1 $$(($(s_count)+1)) ); do\
		csplit /workspaces/book/src/$(book)/$$i/$$i.md '/^### .*/' {$$(($$(grep -o -i '^### ' /workspaces/book/src/$(book)/$$i/$$i.md| wc -l)-1))};\
		for ix in $$(seq 1 $$(($$(ls -1 x*| wc -l)-1)) ); do\
			if [ $$ix -lt 10 ] ; then\
				mv /workspaces/book/src/$(book)/xx0$$ix /workspaces/book/src/$(book)/$$i/$$i$$1_link/$$ix.md;\
			else\
				mv /workspaces/book/src/$(book)/xx$$ix /workspaces/book/src/$(book)/$$i/$$i$$1_link/$$ix.md;\
			fi;\
		done;\
	done
	rm -rf /workspaces/book/src/$(book)/xx00;

html:
	rm -rf /workspaces/book/docs/$(book)
	mkdir -p /workspaces/book/docs/$(book)
	@for i in $$(seq 1 $$(($(s_count)+1)) ); do\
		mkdir -p /workspaces/book/docs/$(book)/$$i;\
		for c in $$(seq 1 $$(ls -1 /workspaces/book/src/$(book)/$$i| wc -l) ); do\
			npx markmap-cli -o /workspaces/book/docs/$(book)/$$i/$$i.html /workspaces/book/src/$(book)/$$i/$$i.md;\
		done;\
		mkdir -p /workspaces/book/docs/$(book)/$$i/$$i$$1_link;\
		for c in $$(seq 1 $$(ls -1 /workspaces/book/src/$(book)/$$i/$$i$$1_link| wc -l) ); do\
			npx markmap-cli -o /workspaces/book/docs/$(book)/$$i/$$i$$1_link/$$c.html /workspaces/book/src/$(book)/$$i/$$i$$1_link/$$c.md;\
		done;\
	done

html_link:
	npx markmap-cli -o /workspaces/book/docs/$(book)/main_link.html /workspaces/book/src/$(book)/main_link.md;
