FROM python:3.8.8-slim-buster

RUN apt-get update && \
    apt-get install -y \
        build-essential \
        libpoppler-cpp-dev \
        pkg-config python3-dev \
        libasound-dev \
        portaudio19-dev \
        libportaudio2 \
        libportaudiocpp0 && \
        apt-get clean


COPY  docker/python38/requirements.txt requirements.txt

RUN pip install -r requirements.txt


ENV DEVELOPER developer
RUN adduser --disabled-password --gecos '' ${DEVELOPER}
USER ${DEVELOPER}

WORKDIR /application