Jekyll
==================
Jekyll:
[http://jekyllrb.com/](http://jekyllrb.com/)

###Supported tags
[```latest```_(jekyll/Dockerfile)_](https://github.com/atomi/public-dockerfiles/blob/master/jekyll/Dockerfile)


###Information
DATA folder is in ```/data```

To RUN this container in your webroot:

```docker run -p 4000:4000 -v `pwd`:/data atomi/jekyll serve --host=0.0.0.0 --force_polling```
