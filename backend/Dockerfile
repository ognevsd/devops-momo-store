FROM golang:1.21.5-bookworm

WORKDIR /usr/src/app
COPY . .

EXPOSE 8081
ENTRYPOINT [ "go", "run", "./cmd/api" ]