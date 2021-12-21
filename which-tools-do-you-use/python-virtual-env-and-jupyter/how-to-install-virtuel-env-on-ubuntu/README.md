---
description: '@Glimpse'
---

# How to install virtuel Env on Ubuntu

@page [source and THX to](https://tech.serhatteker.com/post/2018-12/virtualenv/)

We may face issues when our Linux distribution only offers certain versions of Python and its packages, when we actually need newer or older versions.

We can install new versions of Python on the server, however this will be more complex because we will have some dependency issues when trying to compile everything we need.

Virtual environments make this very easy to manage and set up, we can have different versions of Python and packages in each environment, and it will be isolated from the main system.

```
// Some code
$   sudo apt-get install python3-pip
$   sudo pip3 install virtualenv 
$   cd $YOUR_PROJECT_DIRECTORY
$   virtualenv $NAME   #$NAME is the name of the enviroment
$   source $NAME/bin/activate
### now you see this in the Terminal : ($NAME) ~/$YOUR_PROJECT_DIRECTORY
### you can deactivate the env with $deactivate


```
