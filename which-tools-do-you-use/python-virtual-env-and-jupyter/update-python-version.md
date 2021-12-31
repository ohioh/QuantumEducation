---
description: '@Glimpse Here is a short tutorial to update your python version 3.10'
---

# Update Python Version

@page   [\[ How To Install Python 3.10 on Ubuntu 20.04|18.04 \]](https://computingforgeeks.com/how-to-install-python-on-ubuntu-linux-system/)

lets start with&#x20;

```
sudo apt update
sudo apt install python3.9
```

You can call this python version now in the terminal with $python3.9 but it is not the main python version on your system,yet. $ **`python3 --version`**&#x20;

**`will give you the old version, because it is the "first" python on your system. We have to change it to the right alternative version.`**\
**``**\
**``**sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.\[old-version] 1

Now we add the new version as an alternative\
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.9 2

type the following command to configure the priority status of the versions:

```
sudo update-alternatives --config python3
```

\
with the terminal output\


![\[ source \]](<../../.gitbook/assets/image (21).png>)

If you are not planning to use the old version of Python, remove the [symlink](https://phoenixnap.com/kb/symbolic-link-linux) that contained the previous Python 3 version with:

$ sudo rm /usr/bin/python3

and create a new symlink:

sudo ln -s python3.9 /usr/bin/python3

python3 --version

you are done. READY to rock python!
