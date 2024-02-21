FROM golang:alpine AS builder
WORKDIR /app
COPY . .
RUN go build -o main ./main.go

FROM alpine:3.18
WORKDIR /app
COPY --from=builder /app/config.yaml .
COPY --from=builder /app/main .
EXPOSE 8080

CMD ["/app/main"]
