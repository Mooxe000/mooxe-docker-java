FROM mooxe/base:dev

MAINTAINER FooTearth "footearth@gmail.com"

WORKDIR /root

# system update
RUN \
  apt-get update && \
  apt-get -y upgrade

RUN apt-get install -y zip unzip

RUN curl -s "https://get.sdkman.io" | bash

RUN fish -lc "fisher edc/bass"

RUN echo "\
function sdk\n\
  bass source ~/.sdkman/bin/sdkman-init.sh --no-use ';' sdk \$argv\n\
end" >> ~/.config/fish/config.fish

RUN \
  apt-get autoremove -y && \
  apt-get clean
