help:           ## Show this help.
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'

lint:           ## Does the linting of the program using golangci-lint
	/root/go/bin/golangci-lint run

build:          ## compile the source code of the application to a binary named awesome-api
	make lint
	go build

run:            ## Run the application in background, and write logs into a file named awesome-api.log
	./awesome-api >./awesome-api.log 2>&1 &

stop:           ## Stop the application
	pkill awesome-api

clean:          ## Stop the application. Delete the binary awesome-api and the log file awesome-api.log
	pkill awesome-api || true
	rm -rf awesome-api awesome-api.log

test:          ## Tests for browser responses
	curl http://localhost:9999
	curl http://localhost:9999/health
