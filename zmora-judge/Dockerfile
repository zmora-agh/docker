FROM ubuntu:16.04

RUN apt-get update \
  && apt-get install -qq -y build-essential cmake --fix-missing --no-install-recommends

RUN mkdir /opt/zmora-judge

WORKDIR /opt/zmora-judge

COPY bin/* ./

STOPSIGNAL SIGTERM

CMD ["./zmora-judge", "$ZMORA_RABBITMQ_URI"]
