FROM node:slim

RUN npm install -g less@beta \ 
                   sass \
                   http-server \
                   which \
                   bower \
                   grunt-cli \
                   gulp \
                   yo \
                   generator-angular generator-angular-fullstack generator-angular-component \
                   generator-gulp-angular generator-gulp-webapp \
                   generator-chrome-extension generator-h5bp \
                   react-tools \
                   livereload \
                   matchdep \
                   protractor \
                   wiki \
                   brunch \
                   nodemon \
                   ionic \
                   cordova \                   
                   coffee-script && \
    npm cache clear

RUN apt-get update && \
    apt-get install -yq \
      curl httpie \
      zsh tmux \
      htop \
      vim \
      git && \
    apt-get clean && \
    rm -rf \ 
      /var/lib/apt/lists/* \
      /tmp/*

# Shell Environment
ENV ZDOTDIR /root/.dotfiles

RUN printf "ZDOTDIR=$ZDOTDIR" >> /etc/zsh/zshenv
RUN git clone https://gist.github.com/f74a3f71655940bb849e.git "$ZDOTDIR" && \
    git clone --recursive https://github.com/sorin-ionescu/prezto.git "$ZDOTDIR/.zprezto"

RUN \
    ln -s $ZDOTDIR/.gitconfig ~/.gitconfig && \
    ln -s $ZDOTDIR/.tmux.conf ~/.tmux.conf && \
    ln -s $ZDOTDIR/.vimrc ~/.vimrc && \
    ln -s $ZDOTDIR/.zshrc ~/.zshrc

WORKDIR /data
CMD ["zsh"]
