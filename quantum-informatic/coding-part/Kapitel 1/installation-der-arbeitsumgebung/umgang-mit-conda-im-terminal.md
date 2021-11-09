---
description: >-
  link:
  https://conda.io/projects/conda/en/latest/user-guide/concepts/conda-commands.html
---

# Umgang mit Conda im Terminal

```
// Aktiviere Conda und erstelle eine eigene Umgebung für "quantum"

conda create --name quantum python=3.9

conda activate quantum

//oder deaktiviere mit 

conda deactivate quantum

// alle Envs
conda info --envs

// Kontrolliere die Python Version (->3.9)
python --version

//ein neues Packet ausprobieren

conda create --clone base --name test

// Packetsuche (Managing packages)
conda search searborn 

//Anaconda ermöglicht die Installation von sehr spezielle Versionen
anaconda search seaborn

// Installation
conda install seaborn 

//Alternative Installation für Packet Version 11.2
conda install seaborn=0.11.2

// Auflistung der vorhandenen Installation in Conda ( in der aktuellen Env)
conda list
```
