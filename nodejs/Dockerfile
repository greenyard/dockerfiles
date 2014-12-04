FROM node:latest

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
RUN chsh -s $(which zsh) root && curl -L http://install.ohmyz.sh | zsh

ENTRYPOINT /bin/zsh
