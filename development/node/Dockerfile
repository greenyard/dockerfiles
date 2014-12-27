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

# Install ZSH and oh-my-zsh and grab my dotfiles
RUN curl https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | zsh && \
    curl https://gist.githubusercontent.com/atomi/3b0f64c1ca585b6f1e36/raw/.tmux.conf > /root/.tmux.conf && \
    curl https://gist.githubusercontent.com/atomi/3b0f64c1ca585b6f1e36/raw/.vimrc > /root/.vimrc

RUN echo 'alias bower="bower --allow-root"' >> /root/.zshrc

WORKDIR /data
CMD ["tmux"]
