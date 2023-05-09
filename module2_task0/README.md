# Build an Application using Make
Write a HTTP web server written in the Golang language that listen to incoming HTTP requests on localhost:9999.


## Prerequisites
- Golang in v1.15.*
- NPM v7+ with NodeJS v14.* (stable)
- Python 3 with pip module
- golangci-lint


## Requirements
You are expected to write a `Makefile` to automate the life-cycle of this application:
- A `Makefile` should be present and valid
- The binary `awesome-api` must NOT exist at the beginning, in the source code
- The goals `build`, `run` , `stop`, `clean` test should be implemented and mapped to the life-cycle stages of the same name


## Lifecycle
- “build”: compile the source code of the application to a binary named `awesome-api` (the name `awesome-api` comes from the command `go mod init github.com/<your github handle>/awesome-api`) with the command `go build`. The first build may takes some times.
- “run”: Run the application in background by executing the binary `awesome-api`, and write logs into a file named `awesome-api.log` with the command `./awesome-api >./awesome-api.log 2>&1 &`.
- “stop”: Stop the application with the command `kill XXXXX` where `XXXXX` is the Process ID of the application. For instance: `kill "$(pgrep awesome-api)"`.
- “clean”: Stop the application. Delete the binary `awesome-api` and the log file `awesome-api.log`
- “test”: You want to test it to ensure that it behaves as expected. With the application started, you may want to use the command line `curl` (or your web browser, or the command `wget` or any other HTTP client):
- “help”: Prints out the list of targets and their usage