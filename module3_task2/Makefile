help:           ## Show this help.
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'

build:     ## Generate a website and an API application.
	@go build
	@hugo > /dev/null 2>&1

run:            ## Run the application in background, and write logs into a file named awesome-api.log
	@make build
	./awesome-api > ./awesome-api.log 2>&1 &

lint:           ## Does the linting of the program using golangci-lint
	markdownlint DEPLOY.md

stop:           ## Stop the application
	pkill awesome-api

clean:          ## Cleanup the content of the directory dist/ and stop the application. Delete the binary awesome-api and the log file awesome-api.log
	pkill awesome-api || true
	rm -rf awesome-api awesome-api.log coverage-units.out coverage-integrations.out awesome-website.zip
	rm -rf dist/*

post:           ## Create a new blog post
	hugo new posts/$(POST_NAME).md
	sed -i 's/title: .*/title: "$(POST_TITLE)"/' content/posts/$(POST_NAME).md

test:          ## Tests for browser responses
	make unit-tests
	make integration-tests
	make validate

unit-tests:    ## Execute (successfully) the Golang unit tests
	@go test -v -short -coverprofile=coverage-units.out

integration-tests:     ## Execute (successfully) the Golang integration tests
	@go test -v -tags=integration -coverprofile=coverage-integrations.out

check:         ## Check if there are dead link or a badly written Markdown file
	markdownlint ./content/posts/*.md
	markdown-link-check ./content/posts/*.md

validate:      ## look if the generated HTML respects the W3C syntax
	python3 /opt/W3C-Validator/w3c_validator.py ./dist/index.html || true

package:    ## produces a file awesome-website.zip, containing the binary awesome-api and the directory dist/ directory
	make build
	zip awesome-website.zip awesome-api dist/
