FROM golang:1.4
MAINTAINER CenturyLink Labs <clt-labs-futuretech@centurylink.com>

RUN apt-get update && apt-get install -y upx-ucl make
# Install Docker binary
RUN wget -nv https://get.docker.com/builds/Linux/x86_64/docker-1.3.3 -O /usr/bin/docker && \
  chmod +x /usr/bin/docker
RUN go get github.com/pwaller/goupx

RUN go get -d github.com/tcnksm/gcli
RUN cd $GOPATH/src/github.com/tcnksm/gcli && \
    make install

VOLUME /src
WORKDIR /src

ENTRYPOINT ["gcli"]
CMD ["help"]
