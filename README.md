# erlang

[![License](https://img.shields.io/github/license/voxpupuli/puppet-erlang.svg)](https://github.com/voxpupuli/puppet-erlang/blob/master/LICENSE)
[![Build Status](https://travis-ci.org/voxpupuli/puppet-erlang.svg?branch=master)](https://travis-ci.org/voxpupuli/puppet-erlang)
[![Code Coverage](https://coveralls.io/repos/github/voxpupuli/puppet-erlang/badge.svg?branch=master)](https://coveralls.io/github/voxpupuli/puppet-erlang)
[![Puppet Forge](https://img.shields.io/puppetforge/v/puppet/erlang.svg)](https://forge.puppetlabs.com/puppet/erlang)
[![Puppet Forge - downloads](https://img.shields.io/puppetforge/dt/puppet/erlang.svg)](https://forge.puppetlabs.com/puppet/erlang)
[![Puppet Forge - endorsement](https://img.shields.io/puppetforge/e/puppet/erlang.svg)](https://forge.puppetlabs.com/puppet/erlang)
[![Puppet Forge - scores](https://img.shields.io/puppetforge/f/puppet/erlang.svg)](https://forge.puppetlabs.com/puppet/erlang)

#### Table of Contents

1. [Description](#description)
2. [Setup - The basics of getting started with erlang](#setup)
    * [What erlang affects](#what-erlang-affects)
    * [Setup requirements](#setup-requirements)
    * [Beginning with erlang](#beginning-with-erlang)
3. [Usage - Configuration options and additional functionality](#usage)
4. [Reference - An under-the-hood peek at what the module is doing and how](#reference)
5. [Limitations - OS compatibility, etc.](#limitations)
6. [Development - Guide for contributing to the module](#development)

## Description

This module configures an Erlang package repository and then installs the Erlang language packages.

## Setup

### What erlang affects

* erlang repository files
* erlang package

### Beginning with erlang

Getting started with this module is extremely simple. We've chosen sane defaults for
both Debian/Ubuntu and CentOS/RHEL OS's, so all you have to do is add the following to
your puppet code:

```puppet
include erlang
```

## Usage

All options and configuration can be done through interacting with the parameters
on the main `erlang` class.
These are now documented via [Puppet Strings](https://github.com/puppetlabs/puppet-strings)

You can view example usage in [REFERENCE](REFERENCE.md).

## Reference

See [REFERENCE](REFERENCE.md).

## Limitations

### Bintray repo_source on CentOS/RHEL

By default, CentOS/RHEL use the `packagecloud` repo source.

If one choose to use the `bintray` repo source, then the following "gotcha" should be noted.

The `bintray` erlang repository for CentOS/RHEL systems requires a `repo_version` parameter
that is the major version of erlang that the repository should be configured for.

Example:
```puppet
class { 'erlang':
  repo_source  => 'bintray',
  repo_version => '23',
}
```
