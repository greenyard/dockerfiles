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

# Install ZSH and oh-my-zsh and grab my dotfiles
RUN curl https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | zsh && \
    curl https://gist.githubusercontent.com/atomi/3b0f64c1ca585b6f1e36/raw/.tmux.conf > /root/.tmux.conf && \
    curl https://gist.githubusercontent.com/atomi/3b0f64c1ca585b6f1e36/raw/.vimrc > /root/.vimrc

WORKDIR /data
    
ENTRYPOINT ["tmux"]
