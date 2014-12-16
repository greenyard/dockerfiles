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
                   nodemon \
                   ionic \
                   cordova \                   
                   coffee-script && \
    npm cache clear

RUN apt-get update && \
		apt-get install -yq \
			curl  \
			haskell-platform node \
			libghc-terminfo-dev \
			tmux \
			zsh \
			htop \
			vim \
			git && \
		apt-get clean && \
		rm -rf \ 
		  /var/lib/apt/lists/* \
		  /tmp/*

#   cabal install elm-reactor # not working
RUN	cabal update && \
		cabal install cabal-install && \
		cabal install elm elm-repl elm-get

RUN elm-get install evancz/elm-html

# Install ZSH and oh-my-zsh and grab my dotfiles
RUN curl https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | zsh && \
    curl https://gist.githubusercontent.com/atomi/3b0f64c1ca585b6f1e36/raw/.tmux.conf > /root/.tmux.conf && \
    curl https://gist.githubusercontent.com/atomi/3b0f64c1ca585b6f1e36/raw/.vimrc > /root/.vimrc

RUN bash -c "ln -s /root/.cabal/bin/{elm,elm-doc,elm-get,elm-repl} /usr/local/bin/"
