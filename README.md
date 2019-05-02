# awesome 4.3 deb package for Ubuntu 18.04

This is the Dockerfile that can be used to build the deb package for *Ubuntu 18.04*.

To get a `deb` file just execute next commands:

```sh
$ git clone https://github.com/ewnd9/awesome-deb-docker.git
$ cd awesome-deb-docker/awesome

$ docker build -t awesome:v1 .
$ id=$(docker create awesome:v1)
$ docker cp $id:/root/awesome_4.3.0-0~bionic0_amd64.deb .
$ docker rm -v $id
```

Then, to install, execute

```sh
$ sudo dpkg -i ./awesome_4.3.0-0~bionic0_amd64.deb
$ sudo apt-get -f install  # To install missing dependencies (dpkg doesn't install any dependencies)
```

Tested with clean installation of Ubuntu 18.04 bionic

## Other Versions

- [ubuntu-16.04](https://github.com/elw00d/awesome-deb-docker/tree/ubuntu-16.04-4.3)
