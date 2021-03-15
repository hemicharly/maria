FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
  && apt-get install -y python3-pip python3-dev \
  && cd /usr/local/bin \
  && ln -s /usr/bin/python3 python \
  && pip3 --no-cache-dir install --upgrade pip \
  && apt install -y \
        software-properties-common \
        build-essential \
        libpoppler-cpp-dev \
        pkg-config \
        libasound-dev \
        portaudio19-dev \
        libportaudio2 \
        libportaudiocpp0 \
        libespeak1 \
        libespeak-dev \
        alsa-base \
        alsa-utils \
     && apt-get clean \
     && rm -rf /var/lib/apt/lists/*


COPY docker/python38/requirements.txt requirements.txt
RUN python3 -m pip install -r requirements.txt

WORKDIR /application