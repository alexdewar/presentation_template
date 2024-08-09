FILE_STEM := {{cookiecutter.project_name}}
MARP_PATH := node_modules/@marp-team/marp-cli/marp-cli.js
NODE ?= node
NPM ?= npm

.PHONY: html

html: $(FILE_STEM).html

$(FILE_STEM).html: $(FILE_STEM).md $(MARP_PATH)
	$(NODE) $(MARP_PATH) $<

$(MARP_PATH):
	$(NPM) install
