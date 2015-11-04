# Portefaix Kibana

* Master :
[![Circle CI](https://circleci.com/gh/portefaix/docker-kibana/tree/master.svg?style=svg)](https://circleci.com/gh/portefaix/docker-kibana/tree/master)

* Develop :
[![Circle CI](https://circleci.com/gh/portefaix/docker-kibana/tree/develop.svg?style=svg)](https://circleci.com/gh/portefaix/docker-kibana/tree/develop)


![logo](http://pkgs.alpinelinux.org/assets/alpinelinux-logo.svg)

[Alpine Linux][] is a Linux distribution built around musl libc and BusyBox.
This image is based on the official Alpine Linux.

[Kibana][] is an open source data visualization platform.
Port exported is : `5601`

## Usage

Install [docker compose][] and launch containers :

    $ docker-compose up

You could check *elasticsearch* on : `http://localhost:9200` and Kibana running on `http://localhost:5601/status`

## Supported tags

- `4.0.3` [![](https://badge.imagelayers.io/portefaix/kibana:4.0.3.svg)](https://imagelayers.io/?images=portefaix/kibana:4.0.3 'imagelayers.io')
- `4.1.1` [![](https://badge.imagelayers.io/portefaix/kibana:4.1.1.svg)](https://imagelayers.io/?images=portefaix/kibana:4.1.1 'imagelayers.io')
- `4.2.0` [![](https://badge.imagelayers.io/portefaix/kibana:4.2.0.svg)](https://imagelayers.io/?images=portefaix/kibana:4.2.0 'imagelayers.io')


## License

See [LICENSE](LICENSE) for the complete license.


## Changelog

A [ChangeLog.md](ChangeLog.md) is available.


## Contact

Nicolas Lamirault <nicolas.lamirault@gmail.com>


[Alpine Linux]: http://www.alpinelinux.org

[Kibana]: https://www.elastic.co/products/kibana

[Docker Compose]: https://github.com/docker/compose
