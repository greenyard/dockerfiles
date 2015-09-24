# Raspberry Pi Jetty Docker Container

A docker container for Jetty. Based on Alpine Linux for Raspberry Pi (armhf).
And using OpenJDK7.

## Usage

```docker run -d -p 80:8080 -v $(pwd)/root:/data/root atomi/rpi-jetty```


Where ```$(pwd)/root``` is the root context of your app. ```/data``` dir maps to the Jetty default ```webapps``` dir.

## License

[MIT](LICENSE)
