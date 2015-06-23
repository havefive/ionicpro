使用安装步骤

1.用WebStorm CheckOut下来，或下载zip包https://github.com/havefive/ionicpro

2.npm install

3.安装mongodb,使用homebrew安装,命令$ brew install mongodb
  新建db目录：$ mkdir -p /data/db
  赋权限 $ sudo chown -R /data/db
  启用mongodb  cd /local/Cellar/mongodb/2.6.7/bin
  ./mongo
  新建数据库 use ionic
  增加用户 db.createUser( { user: "ionic", pwd: "123456", roles: [ "readWrite" ] } )

4.配置启动nodebb
  ./nodebb setup
  Welcome to NodeBB!

  This looks like a new installation, so you'll have to answer a few questions about your environment before we can proceed.
  Press enter to accept the default setting (shown in brackets).
  URL used to access this NodeBB (http://localhost:4567)
  Please enter a NodeBB secret (143d6edd-462c-4e44-bc85-6cedf94af5de) 34392960-ca09-4645-b7af-73f860e25c5f
  Which database to use (mongo) **输入mongo**

  20/6 23:25 [32782] - info: Now configuring mongo database:
  Host IP or address of your MongoDB instance (127.0.0.1)
  Host port of your MongoDB instance (27017)
  MongoDB username (ionic)
  Password of your MongoDB database
  Which database to use (0)
  Configuration Saved OK

  第一次会提示配置管理员

  之后启动./nodebb start
  访问localhost://4567




## Installation

[Please refer to platform-specific installation documentation](http://docs.nodebb.org/en/latest/installing/os.html)


# <img alt="NodeBB" src="http://i.imgur.com/mYxPPtB.png" />

[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/NodeBB/NodeBB?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://travis-ci.org/NodeBB/NodeBB.svg?branch=master)](https://travis-ci.org/NodeBB/NodeBB)
[![Dependency Status](https://david-dm.org/nodebb/nodebb.svg)](https://david-dm.org/nodebb/nodebb)
[![Code Climate](https://codeclimate.com/github/NodeBB/NodeBB/badges/gpa.svg)](https://codeclimate.com/github/NodeBB/NodeBB)
[![Documentation Status](https://readthedocs.org/projects/nodebb/badge/?version=latest)](https://readthedocs.org/projects/nodebb/?badge=latest)

**NodeBB Forum Software** is powered by Node.js and built on either a Redis or MongoDB database. It utilizes web sockets for instant interactions and real-time notifications. NodeBB is compatible down to IE8 and has many modern features out of the box such as social network integration and streaming discussions.

Additional functionality is enabled through the use of third-party plugins.

* [Get NodeBB](http://www.nodebb.org/ "NodeBB")
* [Demo & Meta Discussion](http://community.nodebb.org)
* [NodeBB Blog](http://blog.nodebb.org)
* [Documentation & Installation Instructions](http://docs.nodebb.org)
* [Join us on IRC](https://kiwiirc.com/client/irc.freenode.net/nodebb) - #nodebb on Freenode
* [Follow us on Twitter](http://www.twitter.com/NodeBB/ "NodeBB Twitter")
* [Like us on Facebook](http://www.facebook.com/NodeBB/ "NodeBB Facebook")
* [Get Plugins](http://community.nodebb.org/category/7/nodebb-plugins "NodeBB Plugins")
* [Get Themes](http://community.nodebb.org/category/10/nodebb-themes "NodeBB Themes")
* [Help translate NodeBB](https://www.transifex.com/projects/p/nodebb/)

## Screenshots

[<img src="http://i.imgur.com/FLOUuIqb.png" />](http://i.imgur.com/FLOUuIq.png)&nbsp;[<img src="http://i.imgur.com/Ud1LrfIb.png" />](http://i.imgur.com/Ud1LrfI.png)&nbsp;[<img src="http://i.imgur.com/ZC8W39ab.png" />](http://i.imgur.com/ZC8W39a.png)&nbsp;[<img src="http://i.imgur.com/o90kVPib.png" />](http://i.imgur.com/o90kVPi.png)&nbsp;[<img src="http://i.imgur.com/AaRRrU2b.png" />](http://i.imgur.com/AaRRrU2.png)&nbsp;[<img src="http://i.imgur.com/LmHtPhob.png" />](http://i.imgur.com/LmHtPho.png)&nbsp;[<img src="http://i.imgur.com/paiJPJkb.jpg" />](http://i.imgur.com/paiJPJk.jpg)&nbsp;[<img src="http://i.imgur.com/ZfavPHDb.png" />](http://i.imgur.com/ZfavPHD.png)&nbsp;[<img src="http://i.imgur.com/8OLssij.png" />](http://i.imgur.com/8OLssij.png)&nbsp;[<img src="http://i.imgur.com/JKOc0LZ.png"/>](http://i.imgur.com/JKOc0LZ.png)

## How can I follow along/contribute?

* Our feature roadmap is hosted on the project wiki's [Version History / Roadmap](https://github.com/NodeBB/NodeBB/wiki/Version-History-%26-Roadmap)
* If you are a developer, feel free to check out the source and submit pull requests. We also have a wide array of [plugins](http://community.nodebb.org/category/7/nodebb-plugins) which would be a great starting point for learning the codebase.
* If you are a designer, [NodeBB needs themes](http://community.nodebb.org/category/10/nodebb-themes)! NodeBB's theming system allows extention of the base templates as well as styling via LESS or CSS. NodeBB's base theme utilizes [Bootstrap 3](http://getbootstrap.com/) but themes can choose to use a different framework altogether.
* If you know languages other than English you can help us translate NodeBB. We use [Transifex](https://www.transifex.com/projects/p/nodebb/) for internationalization.
* Please don't forget to **like**, **follow**, and **star our repo**! Join our growing [community](http://community.nodebb.org) to keep up to date with the latest NodeBB development.

## Requirements

NodeBB requires the following software to be installed:

* A version of Node.js at least 0.10 or greater
* Redis, version 2.8.9 or greater **or** MongoDB, version 2.6 or greater
* nginx, version 1.3.13 or greater (**only if** intending to use nginx to proxy requests to a NodeBB)

## Installation

[Please refer to platform-specific installation documentation](http://docs.nodebb.org/en/latest/installing/os.html)

## Securing NodeBB

It is important to ensure that your NodeBB and database servers are secured. Bear these points in mind:

1. While some distributions set up Redis with a more restrictive configuration, Redis by default listens to all interfaces, which is especially dangerous when a server is open to the public. Some suggestions:
    * Set `bind_address` to `127.0.0.1` so as to restrict access  to the local machine only
    * Use `requirepass` to secure Redis behind a password (preferably a long one)
    * Familiarise yourself with [Redis Security](http://redis.io/topics/security)
2. Use `iptables` to secure your server from unintended open ports. In Ubuntu, `ufw` provides a friendlier interface to working with `iptables`.
    * e.g. If your NodeBB is proxied, no ports should be open except 80 (and possibly 22, for SSH access)

## Upgrading NodeBB

Detailed upgrade instructions are listed in [Upgrading NodeBB](https://docs.nodebb.org/en/latest/upgrading/index.html)

## License

NodeBB is licensed under the **GNU General Public License v3 (GPL-3)** (http://www.gnu.org/copyleft/gpl.html)
