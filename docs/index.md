# Ordbok

[![Build Status](https://travis-ci.org/eriktaubeneck/ordbok.svg?branch=master)](https://travis-ci.org/eriktaubeneck/ordbok)
[![Coverage Status](https://img.shields.io/coveralls/eriktaubeneck/ordbok.svg)](https://coveralls.io/r/eriktaubeneck/ordbok)
[![Code Climate](https://codeclimate.com/github/eriktaubeneck/ordbok/badges/gpa.svg)](https://codeclimate.com/github/eriktaubeneck/ordbok)
[![Documentation Status](https://readthedocs.org/projects/ordbok/badge/?version=latest)](https://readthedocs.org/projects/ordbok/?badge=latest)
[![PyPI](https://img.shields.io/pypi/v/ordbok.svg)](https://pypi.python.org/pypi/ordbok/)
[![Wheels](https://img.shields.io/pypi/wheel/ordbok.svg)](https://pypi.python.org/pypi/ordbok/)
[![Downloads](https://img.shields.io/pypi/dm/ordbok.svg)](https://pypi.python.org/pypi/ordbok/)
[![License](https://img.shields.io/pypi/l/ordbok.svg)](https://pypi.python.org/pypi/ordbok/)

As your application grows, configuration can get a bit chaotic, especially if you have multiple versions (local, deployed, staging, etc.) Ordbok brings order to that chaos.

Ordbok abstracts the loading of a configuration from YAML files into a Python dictionary, and also has a specific setup for use with Flask. See [TODO](#todo) for plans to expand this.

![Svenska Akademiens ordbok](config.png)
_<a href="http://droemmaskin.deviantart.com/art/Svenska-Akademiens-ordbok-197812735">Svenska Akademiens ordbok</a> by <span class="username-with-symbol u"><a class="u regular username" href="http://droemmaskin.deviantart.com/">droemmaskin</a><span class="user-symbol regular" data-quicktip-text="" data-show-tooltip="" data-gruser-type="regular"></span></span> on <a href="http://www.deviantart.com">deviantART</a>. Provided under [Attribution-NonCommercial-ShareAlike 3.0 Unported](http://creativecommons.org/licenses/by-nc-sa/3.0/legalcode)_

## Basic Usage

Ordbok is designed to allow users to define a hierarchy of YAML configuration files and specify environments. The default configuration has three tiers: `config.yml`, `local_config.yml`, and Environmental Variables. The later tiers override the earlier ones, and earlier configurations can explicitly require certain variables to be defined in a later one. This can be particularly useful when you expect, say, certain variables to be specified in the environment on a production server and want to fail hard and explicitly when that variable isn't present.
