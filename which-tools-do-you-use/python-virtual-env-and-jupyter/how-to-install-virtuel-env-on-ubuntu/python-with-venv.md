---
description: >-
  @glimpse here we go to use the tool "venv" to create a unique or system
  version as virtual envirenment
---

# Python with Venv

### Go to the directory for your project

create the folder $mkdir my\_project

### Create the virtual Env.

The folder of the virtual ennvirenment should be a seperated folder which is not containing content from your project by it self. To controll packages a "requirement.txt" file helps to organize it.

This "requirments.txt" file can be shared to other users to make a fast start in the project avaible.

The virtual env folder ( best practise: "venv" ) dont have to be shared



### Two way to use the Venv

First you could create an env as a copy of your actual python version with the packages from the system with \


```
 python -m venv venv --system-site-packages 
```

Activate the env with&#x20;

```
source my_project/bin/activate
```

You can now control the complete copy  with&#x20;

```
# get all with activated venv
pip list

# or only the local used packages
pip list --local
```

### Create a package Copy to requirements.txt

```
pip freeze > requirements.txt
```

this command create a copy of the acutal copy of the activated env in a text-file
