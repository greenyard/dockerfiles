FROM node:0.10.36

RUN npm install -g node-gyp less@beta node-sass http-server
RUN npm install -g bower grunt-cli gulp yo
RUN npm install -g jshint react-tools browserify uglify-js
RUN npm install -g livereload nodemon ionic protractor
RUN npm install -g matchdep coffee-script

RUN npm cache clear

WORKDIR /data
