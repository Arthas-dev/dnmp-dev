FROM golang:1.13-stretch

RUN go env -w GO111MODULE=on

RUN go env -w GOPROXY=https://mirrors.aliyun.com/goproxy/

RUN go env -w GOSUMDB=sum.golang.google.cn

RUN go env -w GONOPROXY=*.100tal.com
RUN go env -w GOPRIVATE=*.100tal.com
RUN go env -w GONOSUMDB=*.100tal.com



#RUN CGO_ENABLED=0 GOARCH=amd64 GOOS=linux go build -a -o your-application .


#WORKDIR /app
#COPY --from=builder /build/your-application /app/
#COPY --from=builder /build/config /app/config
#COPY --from=builder /etc/passwd /etc/passwd
#COPY --from=builder /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/


WORKDIR $GOPATH/src/hello
ADD ./hello $GOPATH/src/hello
#RUN go build .

EXPOSE 8080

ENTRYPOINT ["./hello"]


