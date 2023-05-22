FROM golang:1.15.8-buster
WORKDIR /app
RUN apt-get update && apt-get install -y hugo make npm curl \
    sudo curl -L https://github.com/gohugoio/hugo/releases/download/v0.84.0/hugo_extended_0.84.0_Linux-64bit.deb -o hugo.deb \
    sudo apt install ./hugo.deb \
    rm hugo.deb \
    sudo npm install -g markdownlint-cli \
    sudo npm install -g markdown-link-check \
    curl -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/master/install.sh | sh -s -- -b $(go env GOPATH)/bin
