FROM golang:1.16.4-alpine3.13 as build

ADD . /app
RUN cd /app && CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

FROM scratch

COPY --from=build /app/app /app

ENTRYPOINT ["/app"]

EXPOSE 8080
