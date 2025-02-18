# HAProxy packaged by Bitnami

## What is HAProxy?

> HAProxy is a TCP proxy and a HTTP reverse proxy. It supports SSL termination and offloading, TCP and HTTP normalization, traffic regulation, caching and protection against DDoS attacks.

[Overview of HAProxy](http://www.haproxy.org/)

Trademarks: This software listing is packaged by Bitnami. The respective trademarks mentioned in the offering are owned by the respective companies, and use of them does not imply any affiliation or endorsement.

## TL;DR

```console
$ docker run --name haproxy bitnami/haproxy:latest
```

## Why use Bitnami Images?

* Bitnami closely tracks upstream source changes and promptly publishes new versions of this image using our automated systems.
* With Bitnami images the latest bug fixes and features are available as soon as possible.
* Bitnami containers, virtual machines and cloud images use the same components and configuration approach - making it easy to switch between formats based on your project needs.
* All our images are based on [minideb](https://github.com/bitnami/minideb) a minimalist Debian based container image which gives you a small base container image and the familiarity of a leading Linux distribution.
* All Bitnami images available in Docker Hub are signed with [Docker Content Trust (DCT)](https://docs.docker.com/engine/security/trust/content_trust/). You can use `DOCKER_CONTENT_TRUST=1` to verify the integrity of the images.
* Bitnami container images are released daily with the latest distribution packages available.


> This [CVE scan report](https://quay.io/repository/bitnami/haproxy?tab=tags) contains a security report with all open CVEs. To get the list of actionable security issues, find the "latest" tag, click the vulnerability report link under the corresponding "Security scan" field and then select the "Only show fixable" filter on the next page.

## Supported tags and respective `Dockerfile` links

Learn more about the Bitnami tagging policy and the difference between rolling tags and immutable tags [in our documentation page](https://docs.bitnami.com/tutorials/understand-rolling-tags-containers/).


* [`2`, `2-debian-10`, `2.5.1`, `2.5.1-debian-10-r17`, `latest` (2/debian-10/Dockerfile)](https://github.com/bitnami/bitnami-docker-haproxy/blob/2.5.1-debian-10-r17/2/debian-10/Dockerfile)

Subscribe to project updates by watching the [bitnami/haproxy GitHub repo](https://github.com/bitnami/bitnami-docker-haproxy).

## Get this image

The recommended way to get the Bitnami haproxy Docker Image is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/bitnami/haproxy).

```console
$ docker pull bitnami/haproxy:latest
```

To use a specific version, you can pull a versioned tag. You can view the [list of available versions](https://hub.docker.com/r/bitnami/haproxy/tags/) in the Docker Hub Registry.

```console
$ docker pull bitnami/haproxy:[TAG]
```

If you wish, you can also build the image yourself.

```console
$ docker build -t bitnami/haproxy:latest 'https://github.com/bitnami/bitnami-docker-haproxy.git#master:2/debian-10'
```

## Why use a non-root container?

Non-root container images add an extra layer of security and are generally recommended for production environments. However, because they run as a non-root user, privileged tasks are typically off-limits. Learn more about non-root containers [in our docs](https://docs.bitnami.com/tutorials/work-with-non-root-containers/).

## Configuration

### Running commands

To run commands inside this container you can use `docker run`, for example to execute `haproxy --version` you can follow the example below:

```console
$ docker run --rm --name haproxy bitnami/haproxy:latest -- --version
```

In order for the container to work, you need to mount your custom `haproxy.cfg` file in `/bitnami/haproxy/conf/`. The following example runs HAProxy with a custom configuration file:

```console
$ docker run --rm --name haproxy -v /path/to/haproxy.cfg:/bitnami/haproxy/conf/haproxy.cfg bitnami/haproxy:latest
```

Using docker-compose:

```yaml
version: '2'
services:

  haproxy:
    image: bitnami/haproxy:latest
    volumes:
      - /path/to/haproxy.cfg:/bitnami/haproxy/conf/haproxy.cfg
```

Check the [official HAProxy documentation](http://cbonte.github.io/haproxy-dconv/2.5/configuration.html) to understand the possible configurations.

## Contributing

We'd love for you to contribute to this container. You can request new features by creating an [issue](https://github.com/bitnami/bitnami-docker-haproxy/issues), or submit a [pull request](https://github.com/bitnami/bitnami-docker-haproxy/pulls) with your contribution.

## Issues

If you encountered a problem running this container, you can file an [issue](https://github.com/bitnami/bitnami-docker-haproxy/issues/new). For us to provide better support, be sure to include the following information in your issue:

- Host OS and version
- Docker version (`docker version`)
- Output of `docker info`
- Version of this container
- The command you used to run the container, and any relevant output you saw (masking any sensitive information)

## License

Copyright &copy; 2022 Bitnami

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
