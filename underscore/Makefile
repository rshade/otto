.PHONY: source
DEPEND=github.com/kevinburke/go-bindata/...
UNDERSCORE_JS='underscore.js'

source: source.go

underscore.js:
	curl -kL http://underscorejs.org/underscore.js > $(UNDERSCORE_JS)
depend: 
	go get $(DEPEND)

source.go: underscore.js depend
	go-bindata -o source.go -pkg underscore $(UNDERSCORE_JS)
	gofmt -w source.go
	head -4 $< >> $@
	mv $< ..
