Rancher CLI
===========

The Rancher Command Line Interface (CLI) is a unified tool to interact with your Rancher server. 

## Installing

You can check the [releases page](https://github.com/rancher/cli/releases) for direct downloads of the binary and add it to your `$PATH` or [build your own](#building-from-source). 

## Setting up Rancher CLI with a Rancher Server 

The CLI needs to know your server address and the credentials required to authenticate with it. 
Rancher CLI will pull this information from a `cli2.json` that is created the first time you run 
`rancher login`. By default this file is located at `~/.rancher/cli2.json`. 

```
$ rancher login https://<RANCHER_SERVER_URL> -t my-secret-token
```

> Note: The `<RANCHER_SERVER_URL>` includes whatever port was exposed when installing Rancher server.

## Usage

For additional usage run `rancher --help`

## Building from source

The binaries will be located in `/bin`.

### Linux binary

Run `make`.

### Mac binary

Run `CROSS=1 make build`

## Docker image

Run `docker run --rm -it -v <path-to-config>:/root/.rancher/cli2.json rancher/cli [ARGS]`.  
Pass in credentials by replacing `<path-to-config>` with your config file for the server.

To build `rancher/cli` just run `make`.  To use a custom Docker repository do `REPO=custom make` and it will produce a `custom/cli` image.

## Contact

For bugs, questions, comments, corrections, suggestions, etc., open an issue in
[rancher/rancher](//github.com/rancher/rancher/issues) with a title starting with `[cli] `.

Or just [click here](//github.com/rancher/rancher/issues/new?title=%5Bcli%5D%20) to create a new issue.

## License
Copyright (c) 2014-2018 [Rancher Labs, Inc.](http://rancher.com)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
