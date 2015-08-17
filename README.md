# Portefaix Kibana

![logo](http://pkgs.alpinelinux.org/assets/alpinelinux-logo.svg)

[Alpine Linux][] is a Linux distribution built around musl libc and BusyBox.
This image is based on the official Alpine Linux.

[Kibana][] is an open source data visualization platform.
Port exported is : `5601`

## Usage

Launch a local Elasticsearch :

    $ docker run -d --name elasticsearch -p 9200:9200 -p 9300:9300 portefaix/elasticsearch

Run Kibana :

	$ docker run -it --name=kibana -p 9090:5601 --link elasticsearch:elasticsearch portefaix/kibana:4.1.1

## Supported tags

- `4.0`
- `4.1.1`

## License

See [LICENSE][] for the complete license.


## Changelog

A [ChangeLog.md][] is available.


## Contact

Nicolas Lamirault <nicolas.lamirault@gmail.com>


[Alpine Linux]: http://www.alpinelinux.org

[Kibana]: https://www.elastic.co/products/kibana
