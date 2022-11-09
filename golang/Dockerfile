FROM golang:1.11 AS builder
RUN mkdir /app
ADD . /app
WORKDIR /app

RUN go build -o main .

FROM scratch
WORKDIR /app
COPY --from=builder /app/main .

CMD ["/app/main"]