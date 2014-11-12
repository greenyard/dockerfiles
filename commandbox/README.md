CommandBox
==================
Ortus Solution's CommandBox:
[http://www.ortussolutions.com/products/commandbox](http://www.ortussolutions.com/products/commandbox)

###Supported tags
[```latest```_(commandbox/Dockerfile)_](https://github.com/atomi/public-dockerfiles/blob/master/commandbox/Dockerfile)


###Information
DATA folder is in ```/data```

To RUN this container in your webroot:

```docker run -v `pwd`:/data atomi/commandbox```


You may want to add an alias to make it easier to scaffold or add

```alias box="docker run -v `pwd`:/data atomi/commandbox"```

Then run normally in your project folder

```box install coldbox```


