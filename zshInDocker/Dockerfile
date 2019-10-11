FROM ubuntu:latest

RUN apt-get update && \
    apt-get install -y sudo \
    curl \
    git-core \
    zsh \
    wget \
    golang \
    make \
    vim 

ENV TERM xterm
ENV ZSH_THEME random

RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true

CMD [ "zsh" ]