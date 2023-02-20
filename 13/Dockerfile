# syntax=docker/dockerfile:1
FROM golang:1.17 as builder
WORKDIR /opt/app
COPY . .
RUN go env -w GOPROXY=https://goproxy.cn
RUN go build -o t13

FROM ubuntu:latest
WORKDIR /opt/app
COPY --from=builder /opt/app/t13 /opt/app/t13
EXPOSE 8080
CMD ["/opt/app/t13"]