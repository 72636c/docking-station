FROM golang:1.23

RUN apt-get update && apt-get install --assume-yes zip

RUN go install github.com/mgechev/revive@latest
RUN go install golang.org/x/lint/golint@latest
RUN go install golang.org/x/tools/go/analysis/passes/shadow/cmd/shadow@latest
