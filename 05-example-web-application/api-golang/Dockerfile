FROM golang:tip-alpine3.23 AS build

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN go build -o api-golang

FROM scratch

COPY --from=build /app/api-golang api-golang

CMD ["/api-golang"]