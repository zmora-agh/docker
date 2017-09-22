FROM ubuntu:16.04

RUN apt-get update \
  && apt-get install -qq -y build-essential cmake bison flex git pkg-config libcap-dev libprotobuf-dev protobuf-compiler --fix-missing --no-install-recommends

RUN mkdir /opt/zmora-judge

WORKDIR /opt/zmora-judge

COPY scripts/* ./

COPY bin/* /usr/bin/
COPY runner/* /usr/bin/
RUN chmod +x /usr/bin/zmora*

COPY nsjail ./nsjail
RUN cd nsjail && make && mv nsjail /usr/bin && cd .. && rm -rf nsjail

STOPSIGNAL SIGTERM

CMD ["./docker-entrypoint.sh"]
