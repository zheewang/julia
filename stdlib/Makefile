default: get

PKG3_VERSION := a554607c939ab73d89c3e7c6a3dd08fd870145e8
PKG3_URL := https://github.com/JuliaLang/Pkg3.jl

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

SHA_VERSION := 79bcc3fd79c1a6cc8678c39b74d721097c5cb2b0
SHA_URL := https://github.com/staticfloat/SHA.jl

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
