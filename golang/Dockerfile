FROM golang:1.11-alpine

RUN apk --update add --no-cache git musl-dev gcc

WORKDIR /app
RUN go get github.com/astaxie/beego && go get github.com/beego/bee
ADD . .
RUN go build -o mathapp

CMD ["./mathapp"]