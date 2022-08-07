FROM golang:1.19-stretch

RUN apt-get update && apt-get install --assume-yes zip

RUN go get -u github.com/mgechev/revive
RUN go get -u golang.org/x/lint/golint
RUN go get -u golang.org/x/tools/go/analysis/passes/shadow/cmd/shadow
