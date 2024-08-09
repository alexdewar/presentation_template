FILE_STEM := {{cookiecutter.project_name}}
MARP_PATH := node_modules/@marp-team/marp-cli/marp-cli.js
NODE ?= node
NPM ?= npm

.PHONY: html pdf all

html: $(FILE_STEM).html

pdf: $(FILE_STEM).pdf

all: html pdf

$(FILE_STEM).html: $(FILE_STEM).md $(MARP_PATH)
	$(NODE) $(MARP_PATH) $<

$(FILE_STEM).pdf: $(FILE_STEM).md $(MARP_PATH)
	$(NODE) $(MARP_PATH) --pdf $<

$(MARP_PATH):
	$(NPM) install
