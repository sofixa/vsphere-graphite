# vSphere to Graphite

Export vSphere stats to graphite.

Written in go as the integration collectd and python plugin posed too much problems (cpu usage and pipe flood).

# Build status

Automatic build by [drone.io](https://drone.io/)

[![Build Status](https://drone.io/github.com/cblomart/vsphere-graphite/status.png)](https://drone.io/github.com/cblomart/vsphere-graphite/latest)

# Extenal dependencies

Naturaly heavilly based on [govmomi](https://github.com/vmware/govmomi).

But also on [daemon](github.com/takama/daemon) which provides simple daemon/service integration.

# Run it

## Deploy

typical GO:

  > go get github.com/cblomart/vsphere-graphite
  
  
The executable should be in $GOPATH/bin/

It can be copied on any "same system" (same: os and cpu platform).

## Configure

You need to know you vcenters, logins and password ;-)

If you set a domain, it will be automaticaly removed from found objects.

Metrics collected are defined by associating ObjectType groups with Metric groups.
They are expressed via the vsphere scheme: *group*.*metric*.*rollup*

An example of configuration file of contoso.com is [there](./vsphere-graphite.json).

You need to place it at /etc/*binaryname*.json (/etc/vsphere-graphite.json per default)

## Run on Commandline

  > vsphere-graphite
  
## Install as a service

  > vsphere-graphite install
  
## Run as a service

  > vsphere-graphite start
  
  > vsphere-graphite status
  
  > vsphere-graphite stop
  
## Remove service

  > vsphere-graphite remove
  
... Sounds about it.

# License


The MIT License (MIT)

Copyright (c) 2016 cblomart

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

 

