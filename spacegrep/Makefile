# Choices for DUNE_PROFILE are 'default' and 'static'.
ifndef DUNE_PROFILE
  DUNE_PROFILE = default
endif
export DUNE_PROFILE

.PHONY: build
build:
	dune build --profile $(DUNE_PROFILE)
	test -e bin || ln -s _build/install/default/bin .

.PHONY: install
install:
	dune install

.PHONY: examples
examples: build
	./scripts/run-examples

.PHONY: test
test:
	dune exec src/test/test.exe

.PHONY: clean
clean:
	git clean -dfX
	rm -rf bin
