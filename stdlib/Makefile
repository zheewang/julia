default: get

PKG3_VERSION := f4139648bfb4cdde34e50947a73f71c7ee8d29a5
PKG3_URL := https://github.com/vchuravy/Pkg3.jl

Pkg3:
	git clone $(PKG3_URL) $@
Pkg3/$(PKG3_VERSION).commit: Pkg3
	git -C $< checkout $(PKG3_VERSION)
	-rm $</*.commit
	touch $@
checkout-pkg3: Pkg3/$(PKG3_VERSION).commit
get-pkg3:  checkout-pkg3
clean-pkg3:
	rm -rf Pkg3

SHA_VERSION := 8f2c9bb537097b661ac91580d18d20af51e5af22
SHA_URL := https://github.com/vchuravy/SHA.jl

SHA:
	git clone $(SHA_URL) $@
SHA/$(SHA_VERSION).commit: SHA
	git -C $< checkout $(SHA_VERSION)
	-rm $</*.commit
	touch $@
checkout-sha: SHA/$(SHA_VERSION).commit
get-sha: checkout-sha
clean-sha:
	rm -rf SHA

get: get-pkg3 get-sha
clean: clean-pkg3 clean-sha

.PHONY: default get clean
