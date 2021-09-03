# node-red-authorization-examples #

This repository contains three examples of user authentication and authorization for Node-RED flows. While they were designed to be immediately usable with the server implemented in [node-red-within-express](https://github.com/rozek/node-red-within-express), all examples may also used in other environments.

## Prerequisites ##

Every example requires the following Node-RED extension

* [node-red-contrib-components](https://github.com/ollixx/node-red-contrib-components)<br>"Components" allow multiply needed flows to be defined once and then invoked from multiple places

Additionally, all examples expect the global flow context to contain an object called `UserRegistry` which has the same format as described in  "node-red-within-express":

* the object's property names are the ids of registered users<br>user ids have no specific format, they may be user names, email addresses or any other data you are free to choose
* the object's property values are JavaScript objects with the following properties, at least (additional properties may be added at will):
  * **Roles**<br>is either missing or contains a list of strings with the user's roles. There is no specific format for role names
  * **Salt**<br>contains a random "salt" value which is used during PBKDF2 password hash calculation
  * **Hash**<br>contains the actual PBKDF2 hash of the user's password

When used outside "node-red-within-express", the following flows allow such a registry to be loaded from an external JSON file called `registeredUsers.json` (or to be created if no such file exists or an existing file can not be loaded) and written back after changes:

![](outside-node-red-within-express.png)

Just import [these flows](outside-node-red-within-express.json), place them on your Node-RED workspace and - if need be - check the "Inject once" setting of the node labelled "at Startup".

For testing and debugging purposes, the [following flow](show-user-registry.json) may also be imported, which dumps the current contents of the user registry onto Node-RED's debug console when clicked:

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
