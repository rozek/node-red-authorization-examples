# node-red-authorization-examples #

This repository contains three examples of user authentication and authorization for Node-RED flows. While they were designed to be immediately usable with the server implemented in [node-red-within-express](https://github.com/rozek/node-red-within-express), all examples may also used in other environments.

## Prerequisites ##

Every example requires the following Node-RED extension

* [node-red-contrib-components](https://github.com/ollixx/node-red-contrib-components)<br>"Components" allow multiply needed flows to be defined once and then invoked from multiple places

![](outside-node-red-within-express.png)
![](show-user-registry.png)

## Basic HTTP Authentication ##

![](basic-auth.png)

### Try yourself ###

![](try-basic-auth.png)

## Cookie-based Authorization ##

![](cookie-auth.png)

### Try yourself ###

![](try-cookie-auth.png)

## Header-based Authorization ##

![](header-auth.png)

### Try yourself ###

![](try-header-auth.png)

## License ##

[MIT License](LICENSE.md)
