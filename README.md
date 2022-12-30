# Use Nginx Reverse Proxy to serve Go Services
Golang served by Nginx reverse proxy.

#  <font color='red'>Installation</font>
* Browse the repository's root
* Build the images 
    - `docker-compose build`
* Start containers 
    - `docker-compose up -d`

After starting containers you can test the Api at:
```url
http://localhost/api/
```

#  <font color='red'>Code Building</font>
Golang is a compiled programming language so to make any changes to your app, you need to build the executable again.
In this repo the build process is done inside the docker-build process.
So when you need to re-compile the code you can follow this steps:

- `docker-compose down`
- `docker-compose build`
- `docker-compose up -d`

To simplify this steps you can create a makefile and group this commands in a single one, or on *nix system you can use this version of the commands: 
```shell
docker-compose down && docker-compose build && docker-compose up -d
```