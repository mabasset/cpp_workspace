FROM debian:12-slim

ARG UID
ARG GID
ARG NAME

RUN apt update -y && apt install -y \
        sudo \
        build-essential \
        git

RUN groupadd -g ${GID} ${NAME} && \
    useradd -m -s /bin/bash -u ${UID} -g ${GID} ${NAME} && \
    usermod -aG sudo ${NAME} && \
    echo "${NAME} ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers