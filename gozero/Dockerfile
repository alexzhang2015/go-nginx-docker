FROM golang:1.19.4-alpine3.17 AS build

RUN apk add --no-cache git

# Set the Current Working Directory inside the container
WORKDIR /go/src/gozero
COPY . .

# We want to populate the module cache based on the go.{mod,sum} files.
COPY go.mod .
COPY go.sum .
RUN go mod tidy

# Build the Go app
RUN go build -o go-zero .

# This container exposes port 8080 to the outside world
EXPOSE 8080

# Run the binary program produced by `go install`
CMD ["./go-zero"]