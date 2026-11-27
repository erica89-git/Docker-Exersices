FROM ubuntu:24.04

WORKDIR /usr/src/app

RUN apt-get update && \
    apt-get install -y wget ca-certificates && \
    wget https://go.dev/dl/go1.16.linux-amd64.tar.gz && \
    tar -C /usr/local -xzf go1.16.linux-amd64.tar.gz && \
    rm go1.16.linux-amd64.tar.gz

ENV PATH="/usr/local/go/bin:${PATH}"

COPY . .

RUN go build

EXPOSE 8080

CMD ["./server"]
