FROM golang:1.13
WORKDIR /go/app
ADD go.mod .
ADD go.sum .
RUN go mod download
CMD go run gateway/gateway.go -endpoint app:50051

# FROM alpine:latest AS build
# RUN apk update
# RUN apk upgrade
# RUN apk add --update go=1.13.10-r0
# RUN apk add --update upx
# WORKDIR /go/src/app
# COPY . .
# WORKDIR /go/src/app/gateway
# RUN CGO_ENABLED=1 GOOS=linux go build -a -o app .
# RUN upx ./app
#
# FROM alpine:latest
# WORKDIR /root/
# COPY --from=build /go/src/app/gateway/app app
# CMD ["./app", "-endpoint", "app:50051"]
