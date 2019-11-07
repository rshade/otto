.PHONY: source
DEPEND=github.com/kevinburke/go-bindata/...

source: source.go

underscore.js:
	curl -kL http://underscorejs.org/underscore.js > $@
depend: 
	go get $(DEPEND)
source.go: underscore.js depend
	go-bindata -f underscore -p underscore -u true < $< 2>/dev/null | grep -v '^//' | gofmt > $@
	head -4 $< >> $@
	mv $< ..
