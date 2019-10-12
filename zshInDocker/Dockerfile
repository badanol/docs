FROM ubuntu:latest

ARG USER_NAME="kwanghui"
ARG USER_PASSWORD="q1w2e3"

ENV USER_NAME $USER_NAME
ENV USER_PASSWORD $USER_PASSWORD
ENV CONTAINER_IMAGE_VER=v1.0.0

RUN echo $USER_NAME
RUN echo $USER_PASSWORD
RUN echo $CONTAINER_IMAGE_VER

RUN apt-get update && \
    apt-get install -y sudo \
    curl \
    git-core \
    zsh \
    wget \    
    make \
    vim \
    npm \
    nodejs && \
    adduser --quiet --disabled-password --shell /bin/zsh --home /home/$USER_NAME --gecos "User" $USER_NAME && \  
    echo "${USER_NAME}:${USER_PASSWORD}" | chpasswd && usermod -aG sudo $USER_NAME

  # the user we're applying this too (otherwise it most likely install for root)
  USER $USER_NAME
  # terminal colors with xterm
  ENV TERM xterm
  # set the zsh theme
  ENV ZSH_THEME agnoster

RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true

CMD [ "zsh" ]