FILE_STEM := {{cookiecutter.project_name}}
MARP_PATH := node_modules/@marp-team/marp-cli/marp-cli.js
MARP_FLAGS ?= --allow-local-files --theme-set imperial-theme.css
NODE ?= node
NPM ?= npm
MARP_CMD := $(NODE) $(MARP_PATH) $(MARP_FLAGS)

.PHONY: html pdf all serve clean

html: $(FILE_STEM).html

pdf: $(FILE_STEM).pdf

all: html pdf

serve: $(MARP_PATH)
	# By default, it uses port 8080, which is likely to be in use by something else
	env PORT=1984 $(MARP_CMD) --server .

clean:
	rm -f $(FILE_STEM).pdf $(FILE_STEM).html

$(FILE_STEM).html: $(FILE_STEM).md $(MARP_PATH)
	$(MARP_CMD) $<

$(FILE_STEM).pdf: $(FILE_STEM).md $(MARP_PATH)
	$(MARP_CMD) --pdf $<

$(MARP_PATH):
	$(NPM) install
