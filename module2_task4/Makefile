help:           ## Show this help.
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'

build: check         ## Generate the website from the markdown and configuration files in the directory dist/.
	hugo

clean:          ## Cleanup the content of the directory dist/
	rm -rf dist/*

post:           ## Create a new blog post
	hugo new posts/$(POST_NAME).md
	sed -i 's/title: .*/title: "$(POST_TITLE)"/' content/posts/$(POST_NAME).md

check:         ## Check if there are dead link or a badly written Markdown file
	markdownlint ./content/posts/*.md
	markdown-link-check ./content/posts/*.md

validate:      ## look if the generated HTML respects the W3C syntax
	python3 /opt/W3C-Validator/w3c_validator.py ./dist/index.html || true
