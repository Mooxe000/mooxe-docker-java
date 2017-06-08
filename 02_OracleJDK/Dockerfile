FROM mooxe/sdkman

MAINTAINER FooTearth "footearth@gmail.com"

WORKDIR /root

# pre system update

  # echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | \
  #   tee /etc/apt/sources.list.d/webupd8team-java.list && \
  # echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | \
  #   tee -a /etc/apt/sources.list.d/webupd8team-java.list && \
  # apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886

RUN add-apt-repository ppa:webupd8team/java -y

# system update
RUN \
  apt-get update && \
  apt-get -y upgrade

# install java
RUN \
  echo debconf shared/accepted-oracle-license-v1-1 select true | \
    debconf-set-selections && \
  echo debconf shared/accepted-oracle-license-v1-1 seen true | \
    debconf-set-selections && \
  apt-get install oracle-java8-installer -y

RUN \
  apt-get autoremove -y && \
  apt-get clean
