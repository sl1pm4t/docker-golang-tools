# Gox (go v1.7)
#
# docker run --rm -v $GOPATH/src:/go/src -w /go/src/github.com/your-account/project pottava/gox:1.7 --osarch "linux/amd64" -output "dist/{{.OS}}_{{.Arch}}"

FROM golang:1.7-alpine

RUN apk --no-cache add --virtual build-dependencies git \
      && go get -u -v github.com/mitchellh/gox \
      && go get -u -v github.com/ahmetalpbalkan/govvv \
      && rm -rf /go/pkg /go/src

ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
WORKDIR $GOPATH
