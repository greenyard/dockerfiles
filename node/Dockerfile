FROM node:slim

RUN npm install -g less@beta \ 
                   sass \
                   which \
                   bower \
                   grunt-cli \
                   gulp \
                   yo \
                   generator-angular \
                   matchdep \
                   wiki \
                   brunch \
                   coffee-script && \
    npm cache clear
RUN apt-get update && \
    apt-get install -y \
      tmux \
      zsh \
      htop \
      vim \
      git && \
    rm -rf \ 
      /var/lib/apt/lists/* \
      /tmp/*

WORKDIR /data

# Install ZSH and oh-my-zsh
RUN curl -L https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | zsh
