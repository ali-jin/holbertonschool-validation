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
- “build”: Generate the website from the markdown and configuration files in the directory `dist/`.
- “clean”: Cleanup the content of the directory `dist/`
- “post”: Create a new blog post whose filename and title come from the environment variables `POST_TITLE` and `POST_NAME`.
- “help”: Prints out the list of targets and their usage
- “check”: ## Check if there are dead link or a badly written Markdown file
- “validate”: ## look if the generated HTML respects the W3C syntax